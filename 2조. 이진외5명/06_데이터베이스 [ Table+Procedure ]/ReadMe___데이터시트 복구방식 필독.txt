[[ Toad를 이용한 Oracle 데이터시트 복구방식 ]]
 
<< 원리 >>
 
테이블의 복구도 연결된 정보에 영향을 받아 연결된다 ( PK-FK )
 
테이블의 스키마정보는 스크립트에서 읽어낸다.
( Schema 스키마는 테이블 구조정보임 )
 
txt파일로 저장된 정보를 형식을 맞춰서 불러옴


 
<< 복구순서 : 부모테이블 → 자식테이블 >>
( PK 추가 후 FK 추가 )
 
1. [메뉴줄] Database - Import - Import Table Data 클릭

2. 복구할 테이블 선택하기 - Show Data 클릭 - Next 클릭
 
3. 복구소스 확장자 형식 선택 → 백업파일 선택 - Next 클릭
 
4. 데이터구분방식 선택 (Comma 기본) - Next 클릭
 
5. 불러올 구간과 날짜방식 선택

	First Row : 2 변경 ( 1은 컬럼이름줄 ) 변경
	Last Row : 미입력시 전체로 인식
	Date Order : 날짜정리방식 설정
	Four Digit Years : 4자리 연도표시
	Leading Zeros in Dates : 날짜에 0표시
	Date Delimiter : 날짜 구분 타입
	Time Delimiter : 시간 구분 타입

6. 결과 확인을 위해 Yes 클릭

	기존에 있던 자료는 흰색바탕
	불러 올 백업자료는 회색바탕

7. PK/FK 등 key상태 확인 후 - Next 클릭

	미리보기 확인 후 - Next 클릭

8. Commit Mode : 확인 방법 결중 후 - Execute ( 실행 ) 클릭

9. 결과리스트 확인 후 자료입력상태 확인 (복구완료)

