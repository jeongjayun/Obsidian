# key : value database
>  데이터를 key-value 로 저장한다. <br>
>  간단해서 실용성은 없고 주로 서브용 디비로 사용

## redis
    1. key value로 저장
    2. 하드웨어를 램에다가 저장함 램이 하드보다 몇백배 빠름
    3. 메인디비에서 사람들이 많이 쓰는 데이터는 레디스에 복사.
       그리고 데이터 꺼낼 때는 레디스에서 꺼내준다.
    4. 캐싱용
    5. 채팅을 위한 pub
    6. 영상 스트리밍
    7. 로그인 기록 저장

# RDB : 관계형 데이터 베이스
> 표 형식으로 저장한다.

대량의 데이터를 저장할 때는
1. oracle
2. mysql
3. sqlite
4. mariadb
5. googleCoudSpanner
6. PostgreSQl
7. SQLServer 등 사용한다.

 데이터베이스 점유율을 보면 관계형 데이터 베이스를 많이 씀.
 **정확도가 중요하면 RDB**

# Graph Database
## Graph Query Language
- ✈︎ 노선
- SNS 친구관계
- 코로나 전염맵
- 추천 서비스
- …

# Document Database
> Collection 안에 Document 들을 만들어서 Json 형태로 저장<br>
> 데이터의 중복제거를 안함 / 정규화를 안함<br>
> 데이터 입출력이 간단한 편<br>
> 분산처리 매우 잘해줌<br>
> DB간 일관성 떨어질 수 있음

## mongoDB, CouchDB
ex . SNS, 실시간 채팅, 게시판, 온라인게임 등

# Column family Database
> 테이블 만들고 로우를 만들고 자유롭게 컬럼 만든다.

# Search
> index 보관에 특화됨<br>
> 검색을 도와주고 실시간 검색어 추천검색어 검색어 오타 교정 등 쉽게 만들 수 있다.<br>
> 검색이 중요한 사이트에는 엘라스틱 서치