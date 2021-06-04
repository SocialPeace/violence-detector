# ABDetector

웹캠을 이용한 실시간 비정상 행동 감지 서비스 

비정상 행동이 포착될 경우 등록된 번호로 텔레그램 알림을 받을 수 있음



# 프로젝트 구동 환경

- windows 10
- cuda v11.0
- cuDnn v8.0.5
- GeForce GTX 1660 SUPER
- vscode
- python 3.7.9
- opencv-4.5.0



# 프로젝트 구성

- image_data: 학습 이미지 데이터 samples(stand, punch, kick, push)
- models: 학습된 yolo 가중치와 설정파일
- video_data: 테스트 비디오 파일
- extract_video: extract_frame.py를 통해 동영상에서 추출한 이미지 frame이 저장되는 폴더
- augmentation: extract_video에 있는 이미지 frame들에 대해서 agumetation을 진행한 결과가 저장되는 폴더
- static: css 및 디자인 파일 폴더
- templates: flask rendering html 폴더
- requirements.txt: 프로젝트 실행에 필요한 모듈 리스트
- opencv_module: 생성한 가상환경에 넣을 opencv dll 파일이 있는 폴더



### 가상환경 설치(폴더에 기 생성된 .venv 가상환경 사용을 권장)

```
python -m venv [가상환경이름]
```



### 가상환경 실행

```
source [가상환경이름]/Scripts/activate
```



### 가상환경 모듈 설치

```
pip install -r requirements.txt
```



#### opencv 모듈 copy

```
opencv_module 폴더의 파일들을 가상환경/lib/site-packages에 삽입
```



### 동영상에서 이미지 frame 추출

```
python extract_frame.py
```



### 이미지 agumentation 

```
python agumentation.py
```



###  이상행동 감지 서비스 실행

####  비디오 파일

```
python run.py --type 0
```



#### 웹캠

```
python run.py --type 1
```

