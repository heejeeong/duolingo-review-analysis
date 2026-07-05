# Duolingo Review Analysis

듀오링고 구글 플레이 리뷰를 바탕으로, 사용자 불만의 핵심 원인과 개선 방향을 분석한 데이터 분석 프로젝트입니다.

## 프로젝트 개요

이 프로젝트는 듀오링고 앱 리뷰를 수집해 평점, 작성 시점, AI 기능 언급 여부, 사용자 유형별 차이를 비교하고, 주요 불만 주제를 찾아내는 것을 목표로 합니다.

노트북과 보고서에서 확인된 핵심 분석 질문은 다음과 같습니다.

- AI 도입 이후 사용자 불만이 증가했는가
- 낮은 평점 리뷰에서 어떤 키워드가 두드러지는가
- 초보자/고급 사용자, 무료/유료 사용자 간 불만 패턴이 다른가
- AI 관련 불만의 중심 주제는 무엇인가

## 데이터

- 데이터 원본: Google Play Store의 Duolingo 리뷰
- 수집 기간: 2018-09-12 ~ 2025-06-19
- 규모: 약 58,000개 리뷰
- 주요 컬럼: `reviewId`, `at`, `score`, `thumbsUpCount`, `content`, `reviewCreatedVersion`, `appVersion`

CSV 파일은 `duolingo_all.csv`에 포함되어 있습니다.

## 사용한 분석 방법

- 리뷰 분포 확인 및 연도별 추이 분석
- 별점별 TF-IDF 키워드 분석
- AI 언급 여부 탐지 및 전후 비교
- 감성 분석
- 학습 레벨/결제 유형 분류
- LDA 토픽 모델링
- 카이제곱 검정
- 워드클라우드 및 시각화

## 주요 결과

- 1점 리뷰에서 AI 관련 키워드가 두드러졌고, 낮은 평점일수록 AI 언급 비율이 높았습니다.
- 2023년 이후 AI 언급 비율이 상승했고, AI가 언급된 리뷰의 평점은 더 낮게 나타났습니다.
- AI 언급 리뷰는 감성 분석에서도 부정 비중이 매우 높았습니다.
- Advanced 사용자와 Paid 사용자는 불만 비율이 높았고, 공통적으로 AI 품질, 업데이트 이후 기능 변화, 결제 및 환불 문제를 많이 언급했습니다.
- AI 관련 불만은 광고/하트/제약 시스템, 학습 방식 불만, AI-first 전환 이후 품질 저하와 같은 주제로 나뉘었습니다.

## 파일 구성

- `TermProject_2021105691남희정.ipynb`: 분석 노트북
- `duolingo_all.csv`: 수집한 리뷰 데이터
- `텀프로젝트1 데이터분석 보고서 남희정.pdf`: 최종 보고서

## 실행 환경

노트북은 Google Colab 기준으로 작성되었으며, 로컬에서 실행할 경우 아래 패키지가 필요합니다.

- pandas
- numpy
- matplotlib
- seaborn
- nltk
- scikit-learn
- transformers
- torch
- pyLDAvis
- wordcloud
- google-play-scraper

### 예시 설치 명령

```bash
pip install pandas numpy matplotlib seaborn nltk scikit-learn transformers torch pyLDAvis wordcloud google-play-scraper
```

NLTK stopwords를 처음 사용하는 경우 아래도 필요할 수 있습니다.

```python
import nltk
nltk.download('stopwords')
```

## 참고

이 프로젝트는 리뷰 데이터에서 사용자 불만의 패턴을 찾고, 특히 AI 도입 이후 체감 품질 변화와 결제 관련 불만을 중심으로 해석하는 데 초점을 맞췄습니다.