### Dockerfile 수정
큰 따옴표로 이루어진 부분에 적절한 값으로 변경
>Your Name => 이름  
>youremail@example.com => 이메일 주소  
>branch Name => 브랜치 이름  

### **이미지 빌드**  
```docker build -t web:v1.1 .```  


### **컨테이너 실행**  
```docker run --name=web -d -t web:v1.1```  


### **vscode 원격 접속**