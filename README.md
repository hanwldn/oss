# README 과제


---


## top 명령어

### top

> 서버 상태를 모니터링 및 점검해야 하는 경우 사용하는 명령어로 
> 동작중인 프로세스의 상태, CPU, 메모리, 시스템부하를 실시간으로 화면에 출력해 줍니다.

### 주요 옵션
> 옵션이 있으나 주로 옵션 없이 top 명령어만 사용합니다.

|옵션|설명|
|---|---|
|-d delay|지정한 시간 간격으로 정보를 출력|
|-n num|지정한 횟수만큼 정보를 출력|
|-p pid|지정한 프로세스 id의 정보만 출력|


### 설명
![top1](https://user-images.githubusercontent.com/91604969/171815050-122b8a0d-2364-40ad-82dc-cefabb53947c.png)

1) 첫 번째 줄
* 현재시간 : 23:49:06
* 서버 가동 후 유지 시간(uptime): up 4:09
* 현재 접속자 수: 0 users
* 평균 부하(1분, 5분, 15분): 0.00, 0.00, 0.00


2) 두 번째 줄
* 프로세스 상태(전체, 실행 중, 유후, 정지, 좀비)


3) 세 번째 줄
* CPU 상태


4) 네 번째 줄
* 메모리 상태


5) 다섯 번째 줄
* swap 메모리 상태


6) 여섯 번째 줄부터 프로세스의 상태
* PID: 프로세스ID
* USER: 소유자
* PR: 우선순위
* NI: nice 우선순위
* VIRT: 가상메모리 사용량
* RES: 실제 물리 메모리 사용량
* SHR: 공유 메모리 사용량
* S: 프로세스 상태


---


## ps 명령어

### ps

> 현재 수행되고(실행되고) 있는 프로세스에 관한 정보 상태를 화면에 출력하는 명령어

### 주요 옵션

|옵션|설명|
|---|---|
|-e|모든 프로세스를 출력|
|-f|풀 포맷으로 보여줌|
|-l|긴 포맷으로 보여줌|
|p, -p|특정 PID의 프로세스를 보여줌|
|-u|특정 사용자의 프로세스를 보여줌|

1) 옵션이 없는 경우

<img width="219" alt="ps1" src="https://user-images.githubusercontent.com/91604969/171818469-ec1febd3-de11-4e4b-ba98-046019a9331d.png">

* PID: 프로세스의 ID 변호
* TT: 프로세스가 수행 중인 터미널 번호
* TIME: 사용한 총 CPU 시간
* CMD: 실제 그 프로세스의 내용


2) ps -l

![ps2](https://user-images.githubusercontent.com/91604969/171818793-63b54971-fc21-4f86-a450-0257fa162a40.png)

* 상세한 정보를 보여줌
* S는 sleep 중단 상태
* R은 run 실행 상태


3) ps -e

![ps3](https://user-images.githubusercontent.com/91604969/171818998-8681c363-9818-40f8-962c-e019dc788cbf.png)

* 시스템 전체 프로세스를 보여줌


4) ps -u [user_name]

<img width="254" alt="ps4" src="https://user-images.githubusercontent.com/91604969/171819296-cfea652e-790c-4615-a80a-2c06e889286f.png">

* user_name 또는 UID의 모든 프로세스를 보여줌
* user_name: 본인 또는 다른 사람의 계정 이름
* UID: 본인 또는 다른 사람의 값
* 위의 사진은 계정아이디가 1000인 프로세스를 출력하는 경우임


5) ps -f

![ps5](https://user-images.githubusercontent.com/91604969/171819555-288ec309-6eeb-43c2-9643-be93a3d5aeb4.png)


6) ps -p 1

<img width="244" alt="ps6" src="https://user-images.githubusercontent.com/91604969/171819627-0c535f73-e2d6-4cf3-a201-ad91415efa72.png">

* 위의 사진은 프로세스의 번호가 1인 프로세스를 출력하는 경우임


---


## job 명령어

### job

> 작업이 중지된 상태, 백그라운드로 진행 중인 작업 상태, 변경되었지만 보고되지 않은 상태등을 표시하는 명령어

### 주요 옵션

|옵션|설명|
|---|---|
|-l|프로세스 그룹 ID를 state 필드 앞에 출력|
|-n|프로세스 그룹 중에 대표 프로세스 ID를 출력|
|-p|각 프로세스 ID에 대한 한 행씩 출력|
|command|지정한 명령어를 실행|


#### 사용법

` jobs [옵션] [작업번호] `


### jobs으로 출력되는 백그라운드 작업의 상태 값

|상태|설명|
|---|---|
|Running|작업이 계속 진행 중임|
|Done|작업이 완료되어 0을 반환|
|Done(code)|작업이 종료되었으며 0이 아닌 코드를 반환했음을 의미|
|Stopped|작업이 일시 중단|
|Stopped(SIGTSTP)|SIGTSTP 시그널이 작업을 일시 중단|
|Stopped(SIGSTOP)|SIGSTOP 시그널이 작업을 일시 중단|
|Stopped(SIGTTIN)|SIGTTIN 시그널이 작업을 일시 중단|
|Stopped(SIGTTOU)|SIGTTOU 시그널이 작업을 일시 중단|


---


## kill 명령어

### kill

> 프로세스를 강제 종료시키는 명령어
> 실행 중인 프로세스를 죽임(-9 옵션을 사용함)

#### 사용법

` kill -9 [죽일 프로세스의 PID] `

![kill1](https://user-images.githubusercontent.com/91604969/171821561-8f40eed9-c8e7-4993-ac01-a05b3352f1b6.png)


---


## vim 에디터 매크로 사용방법

### 매크로

> 지정한 동작 또는 명령을 반복 수행해줌


1) q + [name]

* 매크로 시작(name키에 recording 시작), name키는 임의로 지정 가능


2) 반복을 위한 내가 원하는 동작

* 매크로 입력


3) q

* 매크로 종료(recoding 종료)


4) @[name]

* 매크로 실행(1회 실행)


5) 추가

* @@ : 방금 실행한 매크로 재실행
* [number]@[name] : 매크로 number회 실행
* :u : 작업 되돌리기


