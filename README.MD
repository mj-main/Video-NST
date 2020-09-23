# 1. 개요
- Style Transfer: Content Image와 Style Image를 넣으면 Style이 적용된 Content 이미지가 생성된다.
- 이미지에 대해 Neural Style Transfer를 적용해보고, 이를 비디오에도 적용한다.

# 2. 순서
- Image NST
  - Working Directory 설정하기
  - ImageNet으로 pre-trained된 VGG19 불러오기(F.C layer 제거)
  - 이미지 로드 및 전처리하기
  - Content 모델과 Style 모델 생성하기
  - 생성된 모델에 content 이미지와 style 이미지 입력하기
  - synthesized image에 대해 content loss와 style loss를 최적화하기
  - 최적화된 synthesized image 나타내기(display 전에 deprocessing 필요)
  
- Video NST
  - 원본 비디오를 개별 프레임으로 나누기(data 폴더에 저장)
  - 개별 프레임에 Image NST 적용하기(output 폴더에 저장)
  - 개별 프레임을 비디오로 합치기

# 3. 주요사항
  - NST 방법으로는 Pre-trained CNN을 사용하는 방식 외에도, style domain에 대해 모델을 학습시켜서 Feedforward 모델 얻을 수 있다.
  - colab에서 짧은 길이의 영상을 처리하는데에도 시간이 상당히 소요된다. (5s * 30fps = 약 150장 처리에 30분 소요)
  
