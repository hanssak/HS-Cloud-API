Swagger 연동: https://app.swaggerhub.com/apis/hanssak/IW-API/1.0.0



## REST 설계 시 규칙
 
### 1. 기본 CRUD를 규범
	- POST: create
	- GET: read
	- PUT: update
	- DELETE: delete

### 2. Partial Response 처리
	- 응답메세지의 필드 제한
	- /users/nk915?fields=id,name,email
 
### 3. 페이징
	- 리스트 내용 응답 페이징 처리 (추후 설계 예정)
 
### 4. API버전관리
	-  {servicename}/{version}/{REST URL}
		○ Ex) api.server.com/gatekeeper/1.0/users
	- 패치 운영관리 편리함을 위함

### 5. 검색 조건
	-  /user?q=name%3Dcho,region%3Dseoul&offset=20&limit=10

### 6. Response 처리
	- 참고 자료 - https://en.wikipedia.org/wiki/List_of_HTTP_status_codes
	- 200: 성공
	- 201: 생성 성공
	- 400: Bad Request - field validation 실패
	- 401: Unauthorized - API 인증, 인가 실패
	- 404: Not found - 해당 리소스 없음
	- 500: Internal Server Error - 서버 에러


### 7. 관리포털과 서비스포털 구분
	- 관리포털: URL/구분자
	- 서비스포털: URL/고객사ID/구분자 