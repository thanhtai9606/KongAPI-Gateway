1. Lưu ý set konga + kongapi-getway cùng 1 network kong-net
2. Nếu set các Api khác tốt nhất set tất cả về cùng 1 network là bridge thì sẽ map dễ hơn

Set Plugin key-auth
Chả biết tại sao set trực tiếp từ KongA bị lỗi ko xác thực được
sử dụng lệnh thì được
1. curl -i -X POST --url https://localhost:8001/plugins --data 'name=key-auth'  --> Auhtorization for all routes inside
 (curl -i -X POST --url https://localhost:8001/apis/pythian-blog/plugins --data 'name=key-auth') => authorization for specific route
2. Create account (Can also create from KongA or terminal ) after select username => create API Key
3. Validate with postman or terminal
select API-KEY in postman with 
    - key: apikey
    - value: <screte-key-with-user-account>
Terminal 
curl -i -X GET http://localhost:8000/student/getall --header "Host: localhost" --header "apikey: abc123"
