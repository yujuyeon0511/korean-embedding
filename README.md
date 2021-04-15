# korean-embedding
한국어 임베딩 스터디 내역을 기록합니다.

### Peoples
* Dong-Hun Yang
* Ik-Je Choi
* Ju-Yeon Yu

# code

본 레파지토리의 디렉토리 및 코드 구조는 다음과 같습니다.

- `docker` : 도커 환경 구성을 위한 `Dockerfile`이 있습니다. CPU, GPU 버전을 구분합니다.
- `docs` : 튜토리얼 페이지와 관련한 마크다운 문서 등이 있습니다.
- `models` : 임베딩 기법 관련 핵심 코드가 모여 있습니다.
  - `bert` : BERT 모델 (저자 original 코드)
  - `bilm` : ELMo 모델 (저자 original 코드)
  - `swivel` : Swivel 모델 (저자 original 코드)
  - `xlnet` : XLNet 모델 (저자 original 코드)
  - `sent_eval.py` : 문장 임베딩 평가 코드
  - `sent_utils.py` : 문장 임베딩 학습 관련 유틸
  - `train_elmo.py` : ELMo 프리트레인 코드 (저자 original 코드, 하이퍼파라미터 일부 수정)
  - `tune_utils.py` : 임베딩 파인튜닝 관련 유틸
  - `visualize_utils.py` : 임베딩 시각화 관련 유틸
  - `word_eval.py` : 단어 임베딩 평가 코드
  - `word_utils.py` : 단어 임베딩 학습 관련 유틸
- `preprocess` : 말뭉치 전처리 관련 코드가 모여 있습니다.
  - `dump.py` : 원시 말뭉치(raw corpus)를 1개 라인(line)이 1개 문서인 순수 텍스트 파일로 변환하는 유틸
  - `mecab-user-dic.csv` : 은전한닢(mecab) 형태소 분석기의 사용자 사전을 추가하기 위한 입력 파일
  - `supervised_nlputils.py` : KoNLPy, Khaiii 등 지도학습 기반 형태소 분석기 유틸
  - `unsupervised_nlputils.py` : soynlp, sentencepiece 등 비지도학습 기반 형태소 분석기 유틸
- `preprocess.sh` : 말뭉치 전처리 자동화 스크립트 모음
- `sentmodel.sh` : 문장 수준 임베딩 자동화 스크립트 모음
- `wordmodel.sh` : 단어 수준 임베딩 자동화 스크립트 모음


# Reference
- [NLP_tutorial](https://github.com/graykode/nlp-tutorial?files=1')
- [한국어 임베딩 튜토리얼](https://ratsgo.github.io/embedding/)

### book

본 튜토리얼은 다음 도서를 보완하기 위해 작성됐습니다. 도서를 구매하지 않아도 튜토리얼 수행에 문제는 없으나 일부 내용은 도서를 참고해야 그 맥락을 완전하게 이해할 수 있습니다. 다음 그림을 클릭하면 도서 구매 사이트로 이동합니다.

<a href="http://www.yes24.com/Product/Goods/78569687"><img src="https://i.imgur.com/j03ENCc.jpg" width="500px" title="embeddings" /></a>

- [정오표](https://ratsgo.github.io/embedding/notice.html)

### embedding methods

본 튜토리얼에서 다루는 임베딩 기법은 다음과 같습니다.

- 단어 수준 임베딩
  - Latent Semantic Analysis
  - Word2Vec
  - GloVe
  - FastText
  - Swivel
- 문장 수준 임베딩
  - Weighted Embeddings
  - Latent Semantic Analysis
  - Latent Dirichlet Allocation
  - Doc2Vec
  - Embeddings from Language Models (ELMo)
  - Bidirectional Encoder Representations from Transformer (BERT)

### corpus preprocess

임베딩 학습데이터를 만들기 위해서는 전처리(preprocess)를 해야 합니다. 본 튜토리얼에서 다루는 오픈소스 패키지는 다음과 같습니다.

- KoNLPy : http://konlpy.org
- Khaiii : https://github.com/kakao/khaiii
- soynlp : https://github.com/lovit/soynlp
- sentencepiece : https://github.com/google/sentencepiece
