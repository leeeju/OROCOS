
## OROCOS
---

```OROCOS(Open RObot COntrol Software)```는  2000년 12월 로봇 제어 소프트웨어 개발을 위한 오픈 소스 프로젝트로 시작되었으며 벨기에의 K.U.Leuven, 프랑스의 LAAS Toulouse, 그리고 스웨덴의 KTH Stockholm을 주된 파트너로 하여 2001년 시작되어  최근 Orocos Toolchain 2.6.0까지 발표하였다. 기구학 및 동역학 라이브러리(KDL:Kinematics and Dynamics Library), 베이지안 필터링 라이브러리(BFL:Bayesian Filtering Library)와 컴포넌트 제작 및 구동을 위한 툴체인(Orocos Toolchain)을 제공하고 있으며 로봇과 기계 제어에 특화된 컴포넌트 기반의 소프트웨어 프레임웍이다. 

툴체인은 Real-time Toolkit(RTT)와 Orocos Component Library(OCL), 이외에 컴파일을 위한 파일들을 자동 구성하고 생성하는 도구인 AutoProj, OroGen, TypeGen등을 제공한다. RTT는 C++ 기반으로 로봇 관련 응용 프로그램을 작성하기 위한 함수 및 도구로 실시간 컴포넌트를 구성하기 위한 라이브러리 형태이다. OCL은 런타임 컴포넌트 관리를 위한 컴포넌트와 제어 및 하드웨어 접근 처리를 위한 컴포넌트들을 포함하는 유용한 컴포넌트의 모음이다.

KDL은 실시간으로 기구학 및 동역학 모델링 및 연산을 하기 위한 C++라이브러리로서 독립적인 프레임워크를 구성하고 있다. 로봇뿐 아니라 생체 기구학적 모델, 컴퓨터 애니메이션 모델, 기계 도구 모델등조 제공하고 있으며 기구학적 모듈과 모션 계획, RTT와의 결합을 위한 툴 킷을 제공하고 있으며 최근에는 ROS와 통합된 버전을 제공하고 있다.

BFL은 동적 베이지안 네트워크(Dynamic Bayesian Networks)에서 추론을 위한 독립적인 프레임워크로 확장 칼만 필터(Extended Kalman Filters) 및 파티클 필터(Particle Filters) 등 베이즈(Bayes) 규칙에 기초한 반복적 정보 처리 예측 알고리즘과 기국학적 프리미티브로 Frame, Twist, Wrench, 및 각종 변환 그리고 1차 미적분 기능을 제공한다. 

OROCOS에서 컴포넌트는 태스크 컨텍스트(TaskContext) 클래스를 기반으로 구현되고 툴체인의 미들웨어 기능을 통해 배포되고 실행된다. 태스크 컨텍스트는 특정 작업 또는 응용이 실행하는 환경을 정의한다는 의미에서 Context라는 명칭을 사용한다. 실제로는 Operation, Property, Data Port를 설정하는 것으로 컴포넌트의 운영 방식을 결정하도록 되어 있다. [그림 15]는 태스크 컨텍스트를 통해 구성된 컴포넌트의 구조를 나타낸 것으로 그림에서 Operation은 외부에서 컴포넌트 내부 기능(function)에 접근하기 위한 서비스 인터페이스에 해당하고 Property는 컴포넌트의 동작 환경을 설정하기 위한 인터페이스에 해당한다. Data Port는 컴포넌트의 데이터 흐름의 통로에 해당하는 것으로 입력 포트와 출력 포트로 구성된다. 

![오로코스](https://user-images.githubusercontent.com/84003327/160514693-5d4aa241-2212-4c55-9f09-34db11ec0e7f.PNG)

OROCOS의 컴포넌트간 통신은 [그림 16]에 보인바와 같이 같은 프로세스내의 경우에는 프로세스 내부(in-process) 통신을 사용하고  서로 다른 프로세스 또는 다른 호스트에 존재하는 컴포넌트간의 통신은 CORBA를 사용하여 구현된다. 같은 호스트 내의 프로세스 간(inter-process) 통신의 경우 POSIX 메시지 큐를 사용하는 방식도 제공하고 있다.

![aa](https://user-images.githubusercontent.com/84003327/160514799-1b5b80dd-333a-4c9c-82df-44b73f2554f3.PNG)

