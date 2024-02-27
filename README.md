# 2023-2 전북대학교 SW 캡스톤디자인 2023
---

해당 프로젝트는 한국국토정보공사(이하 [LX](https://www.lx.or.kr/kor.do)) x 온새미로팀이 함께 진행했습니다.
## 주제
---
「**고정밀 영상을 활용한 소하천 불법 점용 탐지 기법 개발**」
## 목적
---
하천 환경에 대한 국유지 무단 점용과 무분별한 사용으로 인한 피해를 최소화하기 위해 고정밀 영상과 AI 를 활용하여 하천의 불법 점용 의심 지역을 탐지
## 필요성
---
+ 하천의 불법 점유 및 무단 사용은 행정 관리 비용을 증가시키는 주요 요인 중 하나
+ 이러한 불법 활동을 수동으로 모니터링하고 조치를 취하는 것은 많은 인력과 시간을 소모, 이로 인한 행정적 부담 큼
: 고정밀 이미지와 AI 기술을 사용하여 불법 점유 지역을 자동으로 탐지함으로써, 행정 기관은 불필요한 비용을 줄일 수 있음, 장기적으로 행정 효율성을 증가시키고 국가 예산의 낭비를 방지하는 데 기여할 것이며, 이러한 기술적 접근 방식은 하천 토지 관리의 현대화 및 효율성 향상에서 중요한 역할
![image](https://github.com/tjdeo1102/JBNU_Capstone-2023/assets/90824684/6f72dff2-bf0a-49a3-b364-f30eae4db030)
## 1. 무단 점용 기준 설정
---


## 설치
---

1. 먼저 첫번째 트랙을 위해 VSCode에서 터미널에서 다음의 과정으로 Conda 가상환경을 준비해줍니다. (Conda가 설치되었다고 가정)

```"
conda create -n [가상환경명] python=3.8
```
```"
conda activate [가상환경명]
```
   
3. 다음의 필요한 라이브러리들을 설치해줍니다. (파이토치에 관한 설치는 따로 해주셔야 합니다.)

```"
pip install shapely
```
```"
pip install ultralytics
```
   
5. QGIS 3.34 버전을 설치해야 합니다. [다음](https://download.qgis.org/downloads/)의 링크를 통해 설치해주세요.
   
6. 사전에 드론맵을 준비해주세요(별도로 구해야됨, TIF파일 형식만 지원)
   
7. 드론맵에 해당되는 지역의 행정데이터(토지소유정보, DBF파일 형식만 지원)를 다음의 [링크](http://openapi.nsdi.go.kr/nsdi/index.do)를 통해 다운받습니다.
   

## 과정
---

### 첫번째 트랙
+ 1_YOLO폴더의 [README.md](https://github.com/tjdeo1102/JBNU_Capstone-2023/blob/main/1_YOLO/README.md)를 참고해주세요.
   

### 두번째 트랙
+ 2_QGIS폴더의 [README.md](https://github.com/tjdeo1102/JBNU_Capstone-2023/tree/main/2_QGIS)를 참고해주세요.

## 결과
---
두가지 유형을 담고있는 파일이 저장됩니다.

### 결과 이미지 예시
![image](https://github.com/tjdeo1102/JBNU_Capstone-2023/assets/57614322/43c50c82-d033-4ab5-a975-a1885e5fca0b)

(왼쪽의 사진은 모든 과정을 거쳐서 나온 결과 이미지, 오른쪽은 원본 이미지입니다.)
 + 파란색 배경: 필지의 지목이 하천인 곳을 나타냅니다.
 + 초록색 박스: YOLO모델에 의해 예측된 객체의 박스를 나타냅니다.
 + 빨간색 박스: 초록색 박스 중, 불법 의심 객체인 경우를 나타냅니다.

### 불법 의심 객체 정보를 담은 CSV파일
![image](https://github.com/tjdeo1102/JBNU_Capstone-2023/assets/57614322/726f74d4-7a03-404d-9c5d-409daff6b2e3)
   + 파일: 검출된 객체가 있는 이미지 파일
   + 필지 고유번호: 검출된 객체가 포함된 필지의 고유번호
   + 법정동명: 검출된 객체가 포함된 필지의 법정동명
   + 검출된 물체 번호: 모델에 의해 예측된 라벨 번호
   + 지목코드: 검출된 객체가 포함된 지목의 코드
   + 지목명: 검출된 객체가 포함된 지목의 이름
   + Reason: 검출된 객체가 불법인 이유

## 팀
---

|성명|역할|
|:---:|:---:|
| 오주형 |   PM, AI모델 설계    |
| 소부승 | 데이터 전처리, AI모델 설계 |
| 김지성 |  자료 정리 , QGIS 개발  |
| 곽성대 | 데이터 후처리, QGIS 개발 |

## 라이센스
---

MIT ([LICENCE파일](https://github.com/tjdeo1102/JBNU_Capstone-2023/blob/main/LICENSE) 참고)


## 버그 리포트
---

[Issues](https://github.com/tjdeo1102/JBNU_Capstone-2023/issues)를 이용해주세요.
