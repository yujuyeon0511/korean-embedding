# korean-embedding(Spring 2021)
Record the embedding study history.

## Course Information
- This course meets for in-class lecture Wed 16:00PM - 18:00PM (Seminar room No.4 at KISTI).

### Peoples
- [Kyong-Ha Lee](https://github.com/bart7449)
- Dong-Hun Yang
- Ik-Je Choi
- [Ju-Yeon Yu](https://github.com/yujuyeon0511)

## Materials
- Book: 

<a href="http://www.yes24.com/Product/Goods/78569687"><img src="https://i.imgur.com/j03ENCc.jpg" width="500px" title="embeddings" /></a>

- [정오표](https://ratsgo.github.io/embedding/notice.html)

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
- [KoreanEmbedding](https://github.com/jinmang2/KoreanEmbedding)

## Syllabus
|Event|Date|In-class lecture|Materials and Assignments|
|---------|----|-------------|------------|
|Lecture 1|03/03|Course Introduction|
|Lecture 2|03/10|01. 서론<ul><li>1.1 임베딩이란<li>1.2 임베딩의 역할<li>1.3 임베딩 기법의 역사와 종류<li>1.4 주요 용어|Presenter:<ul><li><a href="https://github.com/yujuyeon0511/korean-embedding/files/6315172/korean_embedding_01.pdf">[slide]</a>유주연 |
|Lecture 3|03/17|02. 벡터가 어떻게 의미를 가지게 되는가<ul><li>2.1 자연어 계산과 이해<li>2.2 어떤 단어가 많이 쓰였는가<li>2.3 단어가 어떤 순서로 쓰였는가<li>2.4 어떤 단어가 같이 쓰였는가|Presenter:<ul><li><a href="https://github.com/yujuyeon0511/korean-embedding/files/6535585/ch02-Vector.in.NLP_.pdf">[slide]</a>최익제 |
|Lecture 4|03/24|03. 한국어 전처리<ul><li>3.1 데이터 확보<li>3.2 지도 학습 기반 형태소 분석<li>3.3 비지도 학습 기반 형태소 분석|Presenter:<ul><li><a href="https://github.com/yujuyeon0511/korean-embedding/files/6315992/korean_embedding_03.pdf">[slide]</a>유주연 |
|Lecture 5|04/01|04. 단어 수준 임베딩<ul><li>4.1 NPLM<li>4.2 Word2Vec<li>4.3 FastText|Presenter:<ul><li><a href="https://github.com/yujuyeon0511/korean-embedding/files/6315172/korean_embedding_01.pdf">[slide]</a>양동헌 |
|Lecture 6|04/07|Field study|Presenter:</a>유주연 |
|Lecture 7|04/15|04. 단어 수준 임베딩<ul><li>4.4 잠재 의미 분석<li>4.5 GloVe<li>4.6 Swivel<li>4.7 어떤 단어 임베딩을 사용할 것인가<li>4.8 가중 임베딩|Presenter:<ul><li><a href="https://github.com/yujuyeon0511/korean-embedding/files/6535584/Word.Embedding_.pdf">[slide]</a>최익제 |
|Lecture 8|04/21|Field study|Presenter:</a>유주연 |
|Lecture 9|04/29|05. 문장 수준 임베딩<ul><li>5.1 잠재 의미 분석<li>5.2 Doc2Vec<li>5.3 잠재 디리클레 할당|Presenter:<ul><li><a href="https://github.com/yujuyeon0511/korean-embedding/files/6462552/korean_embedding_05.pdf">[slide]</a>유주연 |
|Lecture 10|05/17|05. 문장 수준 임베딩<ul><li>5.4 ELMo<li>5.2 Doc2Vec<li>5.5 트랜스포머 네트워크|Presenter:<ul><li><a href="https://github.com/yujuyeon0511/korean-embedding/files/6490453/5.-2_ydh.pdf">[slide]</a>양동헌 |
|Lecture 11|05/26|05. 문장 수준 임베딩<ul><li>5.6 BERT|Presenter:<ul><li><a href="https://github.com/yujuyeon0511/korean-embedding/files/6744750/_1.PDF">[slide]</a>최익제 |
|Lecture 12|06/16|06. 임베딩 파인 튜닝<ul><li>6.1 프리트레인과 파인튜닝<li>6.2 분류를 위한 파이프라인 만들기<li>6.3 단어 임베딩 활용<li>6.4 ELMo 활용<li>6.5 BERT 활용<li>6.6 어떤 문장 임베딩을 사용할 것인가|Presenter:<ul><li><a href="https://github.com/yujuyeon0511/korean-embedding/files/6737260/korean_embedding_06.pdf">[slide]</a>유주연 |
|Lecture 13|06/29|06. 임베딩 파인 튜닝<ul><li>6.6 어떤 문장 임베딩을 사용할 것인가(2)|Presenter:<ul><li><a href="https://github.com/yujuyeon0511/korean-embedding/files/6737261/korean_embedding_06.2.pdf">[slide]</a>유주연 |

