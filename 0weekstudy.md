# 0주차 
## 1-1. BigQuery 기초 지식
**데이터는 보통 데이터베이스 테이블 등에 저장**<br> - Database(DB): 데이터의 저장소<br> - Table: 데이터가 저장된 공간(데이터베이스 안에 Table이 존재함), 추출할 때 SQL 사용<br>- 저장된 데이터를 제품(앱, 웹)에서 사용함

데이터의 저장 장소: MySQL, Oracle 등(회사 by 회사)

OLTP(Online Transaction Processing) - 왜 BigQuery가 등장했는가?<br> - 거래를 하기 위해 사용되는 데이터베이스<br> - 중간(보류)가 없는 무결 상태.<br> - 데이터의 추가(INSERT), 데이터의 변경(UPDATE)이 많이 발생<br> - SQL을 사용해 데이터를 추출할 수 있으나, 분석을 위해 만든 데이터베이스가 아니라서 쿼리 속도가 느림.

**SQL(Structured Query Language)**: 데이터베이스에서 데이터를 가지고 올 때 사용하는 언어<br>
&nbsp;ex) 쿼리문, 쿼리 구문, 쿼리를 짠다, SQL 쿼리 등으로 표현

OLAP의 등장<br> - OLTP가 느려서 OLAP가 등장함<br> - OLAP(Online Analytical Processing): 분석을 위한 기능 제공<br> - 데이터 웨어하우스: 데이터를 한 곳에 모아서 저장하는 곳<br> &nbsp; ex) <mark> 구글 클라우드의 OLAP겸 데이터 웨어하우스가 BigQuery <mark>

OLAP의 장점<br> - SQL을 사용해 쉽게 추출 가능<br> - 데이터 웨어하우스를 관리하기 위해 서버를 띄울 필요 없음(구글에서 인프라를 관리함)

**BigQuery를 사용하는 이유**<br> - 회사에서 앱이나 웹에서 Firebase, Google Analytics 4를 활용할 경우<br> - 운영을 적은 비용(인력)으로 진행하기 위해

## 1-2. BigQuery 환경 설정
**BigQuery의 환경 구성 요소**<br> &nbsp;1) **프로젝트**: 하나의 큰 건물(하나의 프로젝트에 여러 데이터셋이 존재할 수 있음) <br>&nbsp;2) **데이터셋**: 프로젝트에 있는 창고(각 창고 공간에 데이터를 저장, 하나의 데이터셋에 다양한 테이블이 존재할 수 있음)<br>&ensp;ex) 판매 데이터, 고객 데이터 등 별도의 데이터<br>&nbsp;3) **테이블**: 창고에 있는 선반(행과 열로 이루어진 데이터들이 저장됨)

## 2-1. 데이터 활용 Overview
## 2-2. 저장된 데이터 활용하기