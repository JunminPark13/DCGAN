# DCGAN
Dog Image Generating (DCGAN) (2020.06.29)<br><br>

2020년도 1학기 '인공지능의이해와활용' 수업 최종 과제로 딥러닝 기술을 활용한 자유주제 프로젝트가 있었다.<br>
DCGAN을 활용하여 새로운 개 이미지 생성을 프로젝트 목표로 하였다.<br><br>

DCGAN은 Convolutional layer를 GAN 네트워크에 적용시킨 구조를 갖는다.<br>
### DCGAN의 특징
- 기존 GAN에서 Linear Layer와 Pooling Layer 최대한 배제 <br>
- Discriminator는 Convolutional Layer를 사용하여 사진에서 이미지 특징 추출<br>
- Generator는 Trnsposed Convolutional Layer를 사용하여 특징 생성<br><br>

### Data 수집
kaggle Cat and Dog Dataset에서 개 사진 다운로드하여 2500장 사용<br>
(https://www.kaggle.com/tongpython/cat-and-dog)<br>
![data](./img/dataset.PNG)
사진 크기 128*128로 일괄 조정<br><br>

### 학습시키기
- Google Colab GPU 사용<br>
- Pytorch 사용<br>
- input image size : 64*64<br>
- 100 epoch동안 학습<br><br>

### 결과
3epoch<br>
![3epoch](./img/result_3epoch.PNG)<br>
50epoch<br>
![50epoch](./img/result_50epoch.PNG)<br>
100epoch<br>
![100epoch](./img/result_100epoch.PNG)<br><br>
100 epoch의 결과 개의 형체가 어느정도 나타나는 새로운 이미지가 생성되는 것을 확인할 수 있었다.<br><br>

### 한계
Training 중, loss가 발산하고 Colab의 RAM 사용량을 초과하는 문제가 있어 원본 이미지 크기를 일괄 조정하고 사진의 해상도를 낮추었다.<br>
그 결과 loss가 발산하고 RAM사용량을 초과하는 문제는 해결할 수 있었지만, 생성해낸 이미지의 해상도 또한 낮았다.<br>
또한, RAM사용량 문제로 인해 많은 epoch 학습시킬 수 없었다.<br>
그 결과 개의 형체인 것은 인지할 수 있었지만, 사람을 속일 수 있을 정도의 결과는 얻지 못했다.<br>
DCGAN 논문에서 사람 얼굴을 생성하는 예시의 결과가 상당히 좋았던 것과는 대조적이어 아쉬웠다.
