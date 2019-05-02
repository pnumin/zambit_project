## Makecode
[마이크로소프트 Makecode](https://github.com/Microsoft/pxt)


Microsoft MakeCode는 오픈 소스 프로젝트인 Microsoft Programming Experience Toolkit (PXT)을 기반의 UI 편집기입니다.

PXT는 컴퓨터 과학 교육에 중점을 두고 초보자들에게 프로그래밍 경험을 만들어 주기위한 특수 목적의 프레임워크입니다.
PXT의 기본 프로그래밍 언어는 TypeScript의 subset(JavaScript 동적 기능 제외)입니다.

### PXT 주요 특징
* 텍스트 형식에 대한 변환기와 함께 블록 기반 코드 편집기
* VS 코드를 지원하는 모나코 코드 편집기
* TypeScript에서 새 블록을 정의하는 확장성 지원
* an ARM Thumb machine code emitter
* command-line 패키지 관리

### git pxt clone 후 로컬호스트에서 수행 
1. 복사할 폴더에서 git clone https://github.com/Microsoft/pxt.git
2. git에서 복사하면 pakage.json이 생성되어 있음으로 npm init는 생략
 * nmp init는 pakage.json 파일을 생성하여 모듈의 의존성을 한꺼번에 관리할 수 있음
3. npm install 
 * package.json 파일 및 해당 종속성에 나열된 모든 모듈을 설치
4. npm run build
 * sciprts를 실행하는 명령어로 scripts에 build명령어 실행
5. npm install -g pxt
 * pxt는 빌드 트리 내 어디서나 실행할 수 있도록 함 (한번만 수행)

### 로컬호스트에서 target 수행 => [로컬호스트 수행 지침](https://makecode.com/cli)

* Command Line Tool
  * pxt : PXT의 Command Line Tool
  * 설치 : npm install -g pxt

* 작업공간 설정하기
  * 모든 pxt target(editor)는 대상 디렉토리를 작성해야 합니다.
  * 마이크로비트 에디터를 설치하기 위해 마이크로비트 디렉토리를 작성하는 방법은 다음과 같습니다.
    * mkdir microbit
    * cd microbit
    * pxt target microbit
      * pxt가 target을 가리 키도록 pxtcli.json 파일을 설정 
      * npm install pxt-microbit과 개념적으로 동일
    * pxt serve
    
* 새 프로젝트 만들기
  * 프로젝트 폴더에 새로운 폴더 생성
    * cd projects
    * mkdir blink
    * cd blink
   * 프로젝트 초기화
     * pxt init
   * 코드 편집(vs code사용)
     * code .
