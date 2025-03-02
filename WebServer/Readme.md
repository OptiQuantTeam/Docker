### **이미지 생성시 {imageName}:{version}을 주의하여 적을 것!!**  


### **이미지 빌드**  
```docker build -t web:v2.1 .```  


### **컨테이너 실행**  
```docker run --name=web -d -t web:v2.1```  


### **vscode 원격 접속**  





```
1. WebServer 폴더를 만든다.
2. 그 안에 다운 받은 Dockerfile을 넣는다. (requirement.txt 파일이 있다면 같이)
3. Dockerfile 안의 코드를 약간 수정한다.
  1) 만약 자신이 개발하던 branch가 없다면 branch Name에 develop을 넣는다.
      그런 다음 5번의 내용까지 완료하고 원격 접속을 한 후 (경로 유의 : /django/CapstoneWeb) 
        git branch -M "개인 branch명"
        git push -u origin "개인 branch명"
      을 입력하여 새로운 branch를 만든다.
  2) 만약 자신이 개발하던 branch가 있다면 branch Name에 해당 branch를 넣는다.
4. 해당 경로의 터미널을 연다. (vscode의 터미널 단축키 : ctrl+`)
5. 아래의 명령어를 입력한다.
```  

### Dockerfile 수정
큰 따옴표로 이루어진 부분에 적절한 값으로 변경
>Your Name => 이름  
>youremail@example.com => 이메일 주소  
>branch Name => 브랜치 이름  
