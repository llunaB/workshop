### AI Cognitive Service 개발과정

(1) Problem Definition

+ 입출력 정의(TASK)
+ 평가방법
+ 응답속도/처리량
+ 배포방법

(2) Data Preparation

+ 데이터 수집
+ 데이터 검증
+ 데이터 정제

(3) AI Modeling

+ 모델 설계
+ 모델 학습
+ 모델 튜닝(하이퍼 파라미터)
+ 모델 평가

(4) Simultaion and Test

+ 시스템 통합
+ 통합테스트
+ 보안검증
+ 라이선스 검증

(5) Deployment

+ Desktop
+ Linux System
+ CPU/GPU



#### 어떤 Task 를할까?

+ 자연어 Task
  + 개체명 인식
  + 감성 분석
  + 텍스트 요약
  + 기계번역
  + 의도분류
  + 기계독해
+ 이미지 Task
  + 이미지 감지
  + 이미지 분류

+ 데이터 수집/라벨링/품질 검사가 가능한가?
+ 가용한 CPU 및 GPU 자원이 있는가?
+ 응답속도/처리량은 어떻게 되는가?

+ 자연어 처리: 기계가 자연어를 이해하도록함



#### 어떤 데이터가 필요할까요?

+ 데이터 수집 / 검증
  + 내부/외부데이터, 웹 크롤링
  + 어노테이션 툴 활용(labeling)
  + 오픈데이터 활용
  + 저작권 확인
+ 데이터 정제
  + 부적합한 문장 제외/ 중복 문장 삭제
  + 문장 부호 오류, 오타 등 수정
  + 개인정보 마스크 및 삭제
  + 이미지 bbox 및 레이블링
  + 이미지 정합성 검토



#### Model 을 만들어 봅시다

+ 모델 설계
  + 딥러닝 프레이워크
  + CPU/GPU
  + 오픈소스 라이선스? 언어모델 사용? (BERT,ALBERT, ELECTRA)
+ Accelerate
  + 모델 학습을 빠르게 할 수 있을까?
  + CPU/GPU 에서 모델 예측을 빠르게 할 수 있을까?
    모델 경량화 고려
+ 모델 학습/튜닝(하이퍼 파라미터)
  + 모델 튜닝 라이브러리
  + Learning Rate
  + Dropout rate
  + Batch Size
  + https://optuna.org/ , https://github.com/hyperopt/hyperopt
+ 모델 평가
  + 모델 평가는 어떻게?
  + 평가 데이터는 있는가? 실제 환경에서 성능이 제대로 나오는가?
  + 모델 관리는 어떻게?



#### 검증을 해봐야죠.

+ 시스템 통합
  + AI서비스 와의 연계가 정상적으로 동작하는가?
  + AI 서비스는 여러 시나리오에서 예상대로 작동하는가?
  + 예외적 상황에 대한 처리가 되어있는가?
+ 코드 인스펙션
  + 정적분석 Rule 확인.(복잡도/중복도/커버리지)
  + SonarQube
+ 보안/오픈소스 검증
  + 오픈 소스 취약점 점검 (Blackduck Hub)
  + 오픈 라이선스 검증 (Blackduck Protex)
  + 보안 검증(Fority)



#### 반영(Deploy) 을 해 볼까요?

+ DevOPs
  + DevOps 환경 정착
  + 서비스 모듈의 MSA
  + CI/CD 컨테이너 기반 배포(Docker)
+ 인프라 요구사항
  + 인프라 요구사항 지표 제공(메모리 점유, 응답시간, 처리량 등)
  + SD(System Architect)는 모델 성능 지표 기반으로 아키텍쳐 구성
+ 체크사항
  + 배포 하드웨어 종류는?
  + Torch 라이브러리 버전은 호스트 OS의 GPU 와 호환이 되는가?



-> GPU 그래픽 카드별로 지원하는 Arch 정보

+ GPU 계열 확인
+ CUDA 버전 확인
+ GPU 와 CUDA 버전에 맞는 Torch 라이브러리 설치



#### VoC가 나왔네요!

+ VOC
  + Why?
  + 도메인 용어를 알아 듣지 못해요.
  + 사용자 개체를 추가하고 싶어요.



+ 실제 부서의 경우, 사회생활을 처음시작하는 분도 많고 젊은 조직이다. 그러나 걱정할 필요가 없는게 조직이 수직 문화에서 수형 문화로 자리잡고 있어서 가서 열심히 배우겠다!! 내 역량을 발휘하겠다!! 이런 마인드만 가지고 있다면, 어떤 조직에서 그렇게 적응하는건 어렵지는 않다고 생각한다.