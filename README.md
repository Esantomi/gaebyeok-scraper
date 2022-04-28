# gaebyeok-scraper
『개벽(開闢)』 전문 스크래퍼 v.0.2

## 개요
- 출처 : [한국사데이터베이스 - 한국근현대잡지자료](http://db.history.go.kr/item/level.do?sort=levelId&dir=ASC&start=1&limit=77&page=1&pre_page=0&setId=-1&totalCount=0&prevPage=1&prevLimit=20&itemId=ma&types=&synonym=off&chinessChar=on&brokerPagingInfo=&levelId=ma_013)
- 목적 : 『개벽(開闢)』의 모든 텍스트와 메타데이터를 excel로 저장
- 제작 : [지해인](https://github.com/Esantomi)

## URL 규칙
- `http://db.history.go.kr/item/level.do?sort=levelId&dir=ASC&start=4&limit=77&page=1&pre_page=0&setId=-1&totalCount=0&prevPage=4&prevLimit=&itemId=ma&types=&synonym=off&chinessChar=on&brokerPagingInfo=&levelId=ma_013_'` + 호(volume) 넘버 4자리_텍스트 넘버 4자리
  - 개벽 제28호는 1부, 2부로 나뉘며, 호 넘버도 각각 271, 272이므로 별도 처리함.
  - 호 처음에 실린 글은 텍스트 넘버가 0 또는 1인 경우가 있으니 별도 처리함.
  - 호 마지막에 실린 사고·편집후기는 텍스트 넘버 끝자리가 1인 경우가 있으니 별도 처리함.
- div 태그의 `#cont_view`에 본문 삽입됨.
- metadata는 tbody > tr > td 안에 있고, tbody는 4개의 tr(순서대로 잡지명, 발행일, 기사제목, 기사형태)을 가짐

## 참고
- `connection reset by peer` error가 뜰 경우, 적당히 `time.sleep(round(random.uniform(3, 5), 2))` 삽입 요망.

## 결과
![image](https://user-images.githubusercontent.com/61646760/165782534-3979624d-a21f-46ad-9e9e-37fab998383a.png)
