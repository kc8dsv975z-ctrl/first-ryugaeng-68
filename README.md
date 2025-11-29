# first-ryugaeng-68
오픈소스sw개론 과제 #2
작성자: 류경연
학번: 20253055
작성일:2025-11-30

---
## 1. top 명령어
###
![top]([https://upload.wikimedia.org/wikipedia/commons/6/6b/Top_in_Linux.png](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAxODAyMDZfNjUg%2FMDAxNTE3ODg0ODU2MDY5.RcIsG2yqUswWLHKmCnEEo0DGFR0ZsQXMZFBGRpfEXHog.Vi1mhn0mdiwJW4wHfqTeGNR7DvGdMfCMC8CZsnlUf_8g.PNG.study2us%2Fimage.png&type=sc960_832))

### 주요 옵션
| 옵션 | 설명 |
|------|------|
| `-n` | 업데이트 횟수 지정 |
| `-d` | 업데이트 간격 설정 |
| `-u` | 특정 유저의 프로세스만 보기 |

---

## 2. ps 명령어
`ps` 명령어는 **현재 실행 중인 프로세스의 목록을 출력하는 명령어**이다.  
`top`과 달리 정적인(멈춰있는) 정보만 보여줌.

### 자주 쓰는 옵션

| 옵션 | 의미 |
|------|------|
| `ps -e` | 모든 프로세스 표시 |
| `ps -f` | 프로세스의 상세 정보 표시 |
| `ps aux` | CPU/메모리 사용량 포함 모든 프로세스 표시 |

### 예시 결과
PID   USER   TIME   COMMAND
123   root   0:00   systemd
456   user   0:01   bash
789   user   5:20   chrome
---

## 3. jobs 명령어
`jobs`는 **현재 쉘에서 백그라운드로 실행되는 작업 목록을 보여주는 명령어**이다.

### 특징
- 터미널에서 `Ctrl + Z` 로 중지한 작업도 표시함
- `&`로 실행한 백그라운드 작업도 조회 가능

### 예시 출력
[1]+  Running   python test.py &
[2]-  Stopped   vim file.txt
---

##  4. kill 명령어
`kill` 명령어는 **프로세스에 신호(SIGNAL)를 보내 종료하거나 제어**하는 명령어이다.

###  대표적인 시그널
| 시그널 번호 | 이름 | 설명 |
|------------|------|------|
| 9 | SIGKILL | 강제 종료 |
| 15 | SIGTERM | 정상 종료 요청 |
| 2 | SIGINT | 인터럽트(Ctrl+C) |

###  사용 예시
```bash
kill 1234       # PID 1234 프로세스 종료
kill -9 1234    # 강제 종료


