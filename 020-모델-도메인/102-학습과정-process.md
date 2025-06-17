# 학습과정 

## 프로세스

### REQ-A 강의계획서 작성

```plantuml
@startuml
skinparam monochrome reverse

title 강의계획서 작성

|관리자|
start
:<<REQ-O>>\n학습과정 관리|
|교수자|
:과목 조회<
:<<command>>\n강의 계획서 작성]
:챕터명, 목적과 목표 입력됨;
:강의 내용 입력됨;
:강의 방법 선정함;
:강의 평가 선정함;
if (평가 등록은 나중에) then (yes)
stop
else (no)
:<<REQ-L>>\n 평가 등록|

stop
@enduml
```

### REQ-O 학습과정 관리

```plantuml
@startuml
skinparam monochrome reverse

title 학습과정 관리 

|관리자|
start
:<<command>>\n학습과정 설계]
if (기존학습과정) then (존재함)
    :차수추가;
    :시작일 입력;
    :일정생성(자동);
else (신규)
    :학습 과정명,목표 입력됨;
    :학습 대상 선정됨;
    :학습 내용, 방법 결정됨;
end if

if (과목등록 여부) then (yes)
else (no)
    |관리자|
    :<<command>>\n과목등록]
    :과목명 입력됨;
    :교수자 선정됨;
end if 
:과목 선정됨<
if (강의 계획서 작성여부) then (작성됨)
else (작성 안됨)
    |교수자|
    :<<REQ-A>>\n강의 계획서 작성|
end if
|관리자|
:강의계획서 조회됨: 시수계산용<
:일정생성;
:설계완료처리;
stop

@enduml
```

