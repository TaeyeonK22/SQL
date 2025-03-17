# 0주차 
## 1-1. BigQuery 기초 지식
- <span style="color:0000ff">**데이터는 보통 데이터베이스 테이블 등에 저장**</span><br>
&nbsp;- Database(DB): 데이터의 저장소<br>
&nbsp;- Table: 데이터가 저장된 공간(데이터베이스 안에 Table이 존재함), 추출할 때 SQL 사용<br>
&nbsp;- 저장된 데이터를 제품(앱, 웹)에서 사용함

- 데이터의 저장 장소: MySQL, Oracle 등(회사 by 회사)

- OLTP(Online Transaction Processing) - 왜 BigQuery가 등장했는가?<br>
&nbsp;- 거래를 하기 위해 사용되는 데이터베이스<br>
&nbsp;- 중간(보류)가 없는 무결 상태.<br>
&nbsp;- 데이터의 추가(INSERT), 데이터의 변경(UPDATE)이 많이 발생<br>
&nbsp;- SQL을 사용해 데이터를 추출할 수 있으나, 분석을 위해 만든 데이터베이스가 아니라서 쿼리 속도가 느림.

- **SQL(Structured Query Language)**: 데이터베이스에서 데이터를 가지고 올 때 사용하는 언어<br>
&nbsp;ex) 쿼리문, 쿼리 구문, 쿼리를 짠다, SQL 쿼리 등으로 표현

- OLAP의 등장<br>
&nbsp;- OLTP가 느려서 OLAP가 등장함<br>
&nbsp;- OLAP(Online Analytical Processing): 분석을 위한 기능 제공<br>
&nbsp;- 데이터 웨어하우스: 데이터를 한 곳에 모아서 저장하는 곳<br>
&nbsp; ex)<span style="color:0000FF"> **구글 클라우드의 OLAP겸 데이터 웨어하우스가 BigQuery** </span>

- OLAP의 장점<br>
&nbsp;- SQL을 사용해 쉽게 추출 가능<br>
&nbsp; - 데이터 웨어하우스를 관리하기 위해 서버를 띄울 필요 없음(구글에서 인프라를 관리함)

- BigQuery를 사용하는 이유<br> - 회사에서 앱이나 웹에서 Firebase, Google Analytics 4를 활용할 경우<br> - 운영을 적은 비용(인력)으로 진행하기 위해

## 1-2. BigQuery 환경 설정
- **BigQuery의 환경 구성 요소**<br>
&nbsp;1) **프로젝트**: 하나의 큰 건물(하나의 프로젝트에 여러 데이터셋이 존재할 수 있음) <br>
&nbsp;2) **데이터셋**: 프로젝트에 있는 창고(각 창고 공간에 데이터를 저장, 하나의 데이터셋에 다양한 테이블이 존재할 수 있음)<br>
&ensp;ex) 판매 데이터, 고객 데이터 등 별도의 데이터<br>
&nbsp;3) **테이블**: 창고에 있는 선반(행과 열로 이루어진 데이터들이 저장됨)

- 생성된 테이블 확인<br>
<img src = "./images/001_projectdatasettable.png" width="100%" height="100%">

## 2-1. 데이터 활용 Overview
- 데이터를 활용하는 과정<br>
&nbsp;어떤 일을 해야 한다<br>&nbsp;-> 원하는 것을 정한다<br>&nbsp;-> 데이터 탐색<br>
&nbsp;-> 데이터에 대해 조건(필터링), 추출, 변환, 요약<br>&nbsp;-> 데이터 결과 검증<br>
&nbsp;-> 피드백/활용<br>
&nbsp;해당 과정에서 <span style="color:0000FF">**데이터 탐색, 데이터 결과 검증 시 SQL을 활용**</span>

- 2-2에서는 단일자료 가정, 조건(필터링)/추출을 어떻게 하는지 배울 예정<br><img src = "./images/002_이어지는강의에서학습할내용.png" width="100%" height="100%">

## 2-2. 저장된 데이터 활용하기
 - <span style="color:0000ff">**SQL 쿼리를 작성하기 전에**</span><br>
 &nbsp;- 데이터가 어떻게 저장되어 있는가를 생각해보기<br>
 &nbsp;- 어떤 데이터가 저장되어 있는가?<br>
 &nbsp;- 칼럼의 의미는 무엇인가?<br>
&nbsp;why? <span style="color:0000ff">**데이터를 제대로 이해**</span>해야 올바른 데이터를 추출할 수 있음<br>
&nbsp;- 예시: 데이터를 추출하기 전에 데이터 웨어하우스에 데이터가 어떻게 저장되어 있는지 확인

- **ERD(Entity Relationship Diagram)**: 데이터베이스의 구조를 한 눈에 알아보기 위해 사용<br>
&nbsp;- 예시<br><img src = "./images/003_ERD예시.png" width="100%" height="100%"><br>
&nbsp;- ERD가 없다면 모든 데이터베이스를 직접 보면서 탐색하면 되는 것이므로, **ERD가 필수적으로 있어야 하는 요소는 아님.**

- 포켓몬 세상을 데이터로 생각해보기<br>
어떤 데이터가 존재할까?<br>
&ensp;- 포켓몬 **(상품)**<br>
&ensp;- 트레이너 **(유저)**<br>
&ensp;- 트레이너가 잡은 포켓몬 **(주문)**<br>
&ensp;- 트레이너가 도전한 유저 배틀<br>
&ensp;- 트레이너가 도전한 체육관 배틀<br>
&ensp;- NPC<br>
&ensp;- 상점<br>
&ensp;- 상점 별로 판매하는 제품<br>
ERD 예시- pokemon<br>
<img src = "./images/004_ERD예시-pokemon.png" width="100%" height="100%">

## 정리 및 느낀점
### SQL의 필요성
&nbsp;SQL은 데이터베이스에서 데이터를 가지고 올 때 사용하는 언어로써 데이터 탐색, 데이터 결과 검증 시 활용 가능한 도구이다. 
<br>다만, 아직은 SQL이 어떤 용도로 활용할 수 있는지, 파이썬과는 별개의 개념인지 잘 모르겠다. 전자의 문제는 강의를 들으면서 해결될 것으로 기대된다.
### 느낀점
&nbsp;SQL은 ADsP를 공부하면서 살짝 들어만 봤던 개념인데, 강의 내용에 따르면 기업에서 많이 활용하는 것 같다.<br>파이썬을 통한 데이터 분석이나 금융 데이터 분석에 관심을 가지고 학회에 들어왔는데, SQL도 활용 가능한 수준까지 공부해 둔다면 데이터 분석 역량이 넓어질 수 있을까..?
### 잘 모르겠는 마크다운 문법(해결 시 취소선)
- -를 입력하면, `·`가 입력될 때도 있고, `-`가 입력될 때도 있는데, 각 기호를 원할 때 사용하는 방법을 잘 모르겠다.
- `&nbsp;`를 입력해서 첫 줄에 들여쓰기를 했을 때, 이어지는 문장이 다음 줄로 넘어가는 경우 두 번째 이하의 줄에서도 해당 들여쓰기 형식을 유지하고 싶은데, 그 방법을 모르겠다.<br>
<img src = "./images/006_0주차마크다운문법.png" width="100%" height="100%">

## 수행 인증샷
<img src = "./images/005_0주차학습인증.png" width="100%" height="100%">
