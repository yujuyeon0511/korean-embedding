# korean-embedding(Spring 2021)
Record the embedding study history.

## Course Information
- This course meets for in-class lecture Wed 16:00PM - 18:00PM (Seminar room No.4 at KISTI).

### Peoples
- Dong-Hun Yang
- Ik-Je Choi
- Ju-Yeon Yu

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
|Lecture 3|03/17|Topics: Machine Learning with Shallow Neural Networks I(<a href="http://www.charuaggarwal.net/Chap2slides.pdf">slides)</a>|Presenter:<ul><li><a href="https://github.com/bart7449/lecture2021a/blob/slides/Mikolov2013b_review_ydh.pdf">[Mikolov13a]</a>(<a href="https://github.com/bart7449/lecture2021a/blob/main/skip-gram%20code%20review.ipynb">code</a>)양동헌 |
|Lecture 4|03/24|Topics: Machine Learning with Shallow Neural Networks II(<a href="http://www.charuaggarwal.net/Chap2slides.pdf">slides)</a>|Presenter:<ul><li><a href="https://github.com/bart7449/lecture2021a/blob/slides/Doc2Vec_review_juyeon.pdf">[Le14a]</a>유주연<li><a href="https://github.com/bart7449/lecture2021a/blob/slides/Bojanowski17a_review_ljy.pdf">[Bojanowski17a]</a>이준영|
|Lecture 5|04/07|Topics:|Presenter:<ul><li>[현장연구]유주연|
|Lecture 6|04/14|Topics: Training Deep Neural Networks II(<a href="http://www.charuaggarwal.net/Chap3slides.pdf">slides</a>)|Presenter:<ul><li><a href="https://github.com/bart7449/lecture2021a/blob/slides/node2vec_Byungyun.pdf">[Grover16a]</a>공병윤   <li><a  |
|Lecture 7|04/21|Topics: Training Deep Neural Networks II(<a href="http://www.charuaggarwal.net/Chap3slides.pdf">slides</a>)<br>Topics: Teaching Deep Learners to Generalize (<a href="http://www.charuaggarwal.net/Chap4slides.pdf">slides</a>)|Presenter:<ul><li>[Ba2016a] |
|Lecture 8|04/28|Topics: Convolutional Neural Networks I(<a href="http://www.charuaggarwal.net/Chap8slides.pdf">slides</a>)|<ul><li>[Glorot10a],[He2015a]양동헌 |
|Lecture 9|05/05|Topics: Convolutional Neural Networks II(<a href="http://www.charuaggarwal.net/Chap8slides.pdf">slides</a>)|Presenter:<ul><li>[Alex12a]송지현<li>[He16a]이건호 |
|Lecture 10|05/12|Topics: Recurrent Neural Networks I(<a href="http://www.charuaggarwal.net/Chap7slides.pdf">slides</a>)|Presenter:<ul><li>[He16b]김정민<li>[Huang17a]이준영<li>[Hu2018]김형민 |
|Lecture 11|05/19|Topics:Recurrent Neural Networks II(<a href="http://www.charuaggarwal.net/Chap7slides.pdf">slides</a>)|No assignments | 
|Lecture 12|05/26|Topics: Attention and Language Model I(slides)|Presenter:<ul><li>[Badahnau16]유주연<li>[Vaswani17a]전호범|
|Lecture 13|06/02|Topics: Attention and Language Model II|Presenter:<ul><li>[Devlin19a]송지현 |
|Lecture 14|06/09|Topis: Lightweight Model<ul><li>Quantized Neural Networks|Presenter:<ul><li>[Rastegary16a]공병윤<li>[Stock20a]김형민|
|Lecture 15|06/16|Final Exam|No Assignments | 

