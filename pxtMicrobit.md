## micro:bit target for PXT

pxt-microbit는 BBC 마이크로 비트를 프로그래밍 할 수있는 PXT target입니다.

## Developer Setup
### Clone the pxt repository
1. 복사할 폴더에서 git clone https://github.com/Microsoft/pxt.git
2. git에서 복사하면 pakage.json이 생성되어 있음으로 npm init는 생략
 * nmp init는 pakage.json 파일을 생성하여 모듈의 의존성을 한꺼번에 관리할 수 있음 
3. npm install 
 * package.json 파일 및 해당 종속성에 나열된 모든 모듈을 설치 
4. npm run build
 * sciprts를 실행하는 명령어로 scripts에 build명령어 실행 
5. cd..

### Clone the pxt-common-packages repository 
6. git clone https://github.com/microsoft/pxt-common-packages
7. cd pxt-common-packages
8. npm install
9. cd..

### Clone pxt-microbit repository
10. git clone https://github.com/microsoft/pxt-microbit
11. cd pxt-microbit
12. npm install -g pxt
 * pxt는 빌드 트리 내 어디서나 실행할 수 있도록 함 (한번만 수행) 
13. npm install

### pxt-microbit을 기본 pxt repo에 연결
14. npm link ../pxt
15. npm link ../pxt-common-packages

### 개발 환경 폴더 구조
 makecode
          |
  ----------------------------------
  |       |                        |
 pxt      pxt-common-packages  pxt-microbit
