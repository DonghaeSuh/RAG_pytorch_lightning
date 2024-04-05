# RAG_pytorch_lightning

## 소개
RAG 논문 속 RAG Token 방식으로 MRC 문제를 풀도록 구현했습니다.

**Reference** : [Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](https://arxiv.org/abs/2005.11401)

## 구조
![image](https://github.com/DonghaeSuh/RAG_pytorch_lightning/assets/82081872/6051cc0e-4691-48be-b3e0-6c97aa150f60)

## 상세한 코드 및 학습 원리 정리
[블로그 링크](https://blog.naver.com/gypsi12/223363251966)


## 코드 설명
- **indexing.ipynb**
  - wikipedia_document를 passage단위로 chunking하고 임베딩 시킨 후, FAISS index를 만들어 저장합니다.

- **wiki_token.ipynb**
  - wikipedia_document를 passage단위가 아닌 OpenAI의 fast BPE tokenizer인 tiktoken을 사용해
    - 특정 chunk_size와
    - chunk_overlap을 만족하는 chunk를 만들 수 있습니다.
  - 이를 이용해 indexing.ipynb에서 임베딩시킨 후, FAISS index를 만들 수 있습니다.
 
- **rag_token_train.py & rag_token_run_test.ipynb**
  - rag_token 방식으로 구현된 Generation based RAG 모델을 학습할 수 있는 코드 및 테스트해볼 수 있는 코드입니다.
  - 내부 config를 바꿔주신 후, ```python train.py``` 하시면 학습 가능합니다.
 
- **rag_token_variant_train.py**
  - rag_token 방식이 아닌 변형버전의 코드입니다.
  - 내부 config를 바꿔주신 후, ```python train.py``` 하시면 학습 가능합니다.
    
