---
title: "실행계획과 튜닝"
order: 1
editable : false
tocDepth: 1
---

## :worried: 이걸 왜해!?

웹 개발을 하면서 여러 프로젝트를 진행했었는데 항상 오라클을 사용했었다.

데이터도 적고, 트래픽도 적은 프로젝트들이라 적당히 쿼리 짜도 결과가 빠르게 나왔었다.

최근 프로젝트에서는 MariaDB를 사용하고 대용량 데이터를 다루고있어 좋은 쿼리를 만들어야한다.

더 좋은 쿼리를 짜고자 실행계획 보는 법과 튜닝에 대해 공부하고 흔적을 남기도록 하겠다!:thumbsup::thumbsup::thumbsup:

## :floppy_disk: 테스트 테이블

SQL문과 함께 실행계획과 튜닝을 해볼꺼라서 기본적인 TABLE을 생성해놨다!

| TABLE NAME              | Description           |                                                                                                                                                                                                                                      |
|-------------------------|-----------------------|
| DEPARTMENT              | 부서 테이블             |
| DEPARTMENT_EMPLOYEE     | 부서와 사원 매핑 테이블   |
| DEPARTMENT_MANAGER      | 부서의 관리자 테이블      |
| EMPLOYEE                | 사원 테이블              |
| EMPLOYEE_ACCESS         | 사원출입기록 테이블       |
| EMPLOYEE_RANK           | 사원직급 테이블          |
| SALARY                  | 급여 테이블             |
                                                                                                                                                                       |
해당 테이블을 가지고 실행계획 및 튜닝을 해보자

<Warning>
- MariaDB version 10.5.16 로 진행
</Warning>

