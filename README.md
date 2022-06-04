**1. 리눅스 명령어 : `top`, `ps`, `jobs`, `kill` 명령어 조사하기**


>### top 명령어 
>>- 동작중인 프로세스 상태를 실시간으로 화면에 출력해주는 명령 
>>- 프로세스 상태 뿐만 아니라 CPU, 메모리, 부하 상태 등도 확인할 수 있음 
>>- top 명령은 실행 상태에서 다양한 명령을 입력하여 프로세스 상태를 출력하거나 제어할 수 있음. 
>
>### 사용법 
>
>> `top [option]`
>
>### 주요 옵션 
>>`-d 갱신 시간` : 갱신 시간 설정 (초 단위) 
>>
>>`-p` : 특정 PID 값을 갖는 프로세스를 모니터링할 때 사용 
>>
>>`-n 값` : top 명령의 실행 횟수를 지정하는 옵션 
>>
>>`-b` : 
 >>- 배치 모드(Batch Mode)로 실행하는 옵션 
 >>- 다른 프로그램이나 파일에 전송할 때 사용 
 >>- 보통 n옵션과 같이 실행 


>### ps 명령어 
>>- Process Status
>>
>>- 동작 중인 프로세스의 상태를 출력해주는 명령 
>
>### ps의 옵션 
>
>>- System V 계열 
>>: 옵션 사용 시, 1개의 대시(Dash, -)를 사용
>>- BSD 계열 
>>: 옵션 사용 시, 대시(-)를 사용하지 않음 
>>- GNU 계열 
>>: 옵션 사용 시, 2개의 대시(--)를 사용 
>>
>*원하는 프로세스 상태를 출력하려면 정확한 옵션 사용이 중요* 
>>Ex) ps-a 와 ps a 는 전혀 다른 결과를 출력 
>>
>>특히, 동작중인 전체 프로세스를 출력하는 경우 System V 계열과 BSD 계열의 옵션을 정확히 사용해야 함 
>
>### 사용법 
>
>>`ps [option]` 
>
>### 주요 옵션 
>
>>`a` : 터미널과 연관된 프로세스를 출력하는 옵션 
>>보통 x 옵션과 연계하여 모든 프로세스를 출력할 때 사용 
>>(BSD 계열) 
>>
>>`u` : 프로세스의 소유자(user)를 기준으로 출력 
>>
>>`x` : 데몬 프로세스처럼 터미널에 종속되지 않은 프로세스 출력 
>>보통 a옵션과 결합하여 모든 프로세스를 출력할 때 사용 
>>
>>`l` : 프로세스의 정보를 길게(Longly) 보여주는 옵션 
>>우선순위와 관련된 PRI와 NI값을 확인할 수 있음
>>
>>`e` : 해당 프로세스에 관련된 환경 변수 정보를 함께 출력 
>>
>>`f` : 프로세스간의 상속 관계를 트리 구조로 보여줌. 
>>
>>`p` : 특정 PID를 지정할 때 사용 
>>(BSD 계열) 
>>
>>`-A` : 모든(All) 프로세스 출력 
>>'-e 옵션'과 같음 (Entire) 
>>(Sysyem V 계열) 
>>
>>`-e` : 모든 프로세스 출력 
>>'-A 옵션'과 같음 
>>
>>`-a` : 세션 리더(일반적으로 로그인 셀)을 제외하고 터미널에 종속되지 않은 모든 프로세스 출력 >
>>
>>`-f` : 유닉스 스타일로 출력해주는 옵션 
>>UID, PID, PPID 등이 함께 표시됨 
>>
>>`-C 프로세스명` : 지정한 프로세스만 보여줌 
>>
>>`-o 값` : 출력 포멧을 지정하는 옵션 
>>값으로는 pid, tty, time, cmd 등을 지정할 수 있음 
>>
>>`-p` : 특정 PID를 지정할 때 사용 
(System V 계열) 
>>
>>`-u` : 특정 사용자의 프로세스 정보를 확인할 때 사용 
>>사용자를 지정하지 않으면 현재 사용자를 기준으로 정보 출력 


>### jobs 명령어 
>>: 다음의 프로세스 목록을 출력해주는 명령 
>>  백그라운드로 실행중인 프로세스 
>>  현재 중지된 프로세스 
>
>### 사용법 
>
>> `jobs [option]` 
>
>### 주요 옵션 
>
>>`-l` : 프로세스 번호(PID)를 추가로 출력 


>### kill 명령어 
>>: 프로세스 특정한 시그널(Signal)을 보내는 명령 
>>  옵션 없이 실행하면 프로세스 종료 신호(15, TERM, SIGTERM)을 보냄 
>>  보통 중지시킬 수 없는 프로세스를 종료시킬 때 사용 
>
>### 사용법 
>
>> `kill [option] [signal] [PID 또는 %Job_Number]` 
>
>### 주요 옵션 
>
>>`-l` : 시그널 종류 출력 
>
>>`-s signal` : 시그널 이름을 지정 

---

**2. vim 에디터에서 매크로 사용방법에 대하여 조사하기 `(q , @)`**

### Vim 매크로란?  
: Macro 는 Vim 명령어'들'을 기록하고, 이를 반복할 수 있는 기능이다.  
 이전에 Vim Micro Macro(dot command)를 활용해서 이전 명령을 바로 반복할 수 있었다.
 그러나, 이는 이전 명령을 반복할 뿐, '이동 후 명령' 과 같은 작업에 대해서는 그 반복이 불가능하다.  

### Vim Macro  

|매크로|설명|
|:---:|:---:|
|`q{레지스터}`|매크로 기록 시작|
|`q`|매크로 기록 종료|
|`@{레지스터}`|저장된 매크로 실행|
|`@@`|직전에 실행한 매크로 재실행|
|`{반복횟수}@{레지스터}`또는`{반복횟수}@@`|저장된 매크로를 **'반복횟수'** 만큼 재실행|

### q-Vim Macro 기록하기 & 기록 종료하기
1) Normal Mode 에서 q 를 입력하면, 하단 상태표시줄에 q 가 표시

2) 이는 앞으로 기록할 레지스터를 지정해주기를 대기하고 있는 상태

3) 레지스터(a-z, 0-9 중 하나)를 정하여 입력하면 상태표시줄에
'Recording @a'(레지스터로 'a'를 입력했다고 가정) 와 같이 실제 명령어를 대기하고 있는 상태가 됨   

4) 일련의 동작들을 입력한 뒤 다시 q 를 입력하면 매크로 기록이 종료

### @-Vim Macro 실행하기
1) `@{레지스터}` 로 특정 레지스터에 저장된 매크로를 실행시킬 수도 있고

2) `@@` 로 직전에 실행한 매크로를 재실행할 수도 있다
 
### 레지스터에 저장된 매크로 확인해보기  
+ vim 에서는 레지스터에 저장된 내용을 확인하기 위한 command mode 명령어를 제공

+ `:register` 단순히 이 명령어를 입력하면 모든 레지스터의 저장된 값들을 리스팅

+ `:register` 명령어는 인자를 받기도 하는데, `:register a` 와 같이 명령어의 인자로 레지스터명을 전달하면 해당 레지스터에 저장된 값을 표현해줌 
