# 학습과정 

## 유스케이스

```plantuml
@startuml
skinparam monochrome reverse
left to right direction

:교수자: as professor
:관리자: as manager

component learningCourse <<module>> {
    (강의계획서 작성) as req_a <<REQ-A>>
    (학습과정 관리) as req_o <<REQ-O>>

}

[데이터 변경이력] <<REQ-NF8>>
[회원관리] <<REQ-NF2>>
[마스터코드 관리] <<REQ-NF9>>
[휴일관리] <<REQ-NF10>>
[첨부파일관리] <<REQ-NF11>>

professor --> req_a
manager -up-> req_o
learningCourse ...> [데이터 변경이력]
learningCourse ...> [회원관리]
learningCourse ...> [마스터코드 관리]
learningCourse ...> [휴일관리]
learningCourse ...> [첨부파일관리]
@enduml
```
