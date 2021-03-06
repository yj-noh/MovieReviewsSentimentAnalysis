# MovieReviewsSentimentAnalysis

1)	영화 리뷰 데이터 “2016_movie_review.txt” 파일의 감성 분석을 위해 전처리 과정에서 형태소 분석기는 ‘Mecab’을 이용하였으며, 여러 품사 중 명사, 동사, 형용사만 추출하였다. 또한 '의', '가', '이', '은' 등 감성 분석에 불필요한 불용어들을 제거하였다.

2)	평점 기준으로 긍정 또는 부정의 값을 갖는 새로운 종속 변수를 생성하고(긍정 평점 8 ~ 10점은 값 = 1, 부정 평점 1 ~ 4점은 값 = 0), 해당 데이터셋을 학습과 평가 데이터셋으로 구분하였다.

3)	CounterVectorizer와 TfidfVectorizer 클래스를 이용한 문서 벡터화 작업 수행 시 모형 성능 비교를 위해 모델링 시 필요한 하이퍼파라미터를 설정할 때 가장 최적의 파라미터 (규제화 종류 penalty, 규제 매개변수 C 값)를 찾아주는 Grid Search + k-fold cross validation 수행하였다.

4)	평가 데이터 셋에 대한 Confusion Matrix를 이용하여 산출할 수 있는 지표 값들과 ROC+AUC score 값을 통해 해당 모델의 예측 성능을 평가하였다.

5)	추가적으로 학습데이터 내 긍정 값은 524,033개, 부정 값은 81,312개로 데이터 개수 차이로 인한 불균형 클래스 문제가 존재한다고 생각됩니다. 이를 해결하기 위해 데이터 개수가 적은 클래스의 표본을 가져온 후 임의의 값을 추가하여 새로운 샘플을 만들어 추가하는 오버샘플링 방식인 SMOTE 기법을 사용하였으며, 성능면에서 개선되었는지 평가하였다.
