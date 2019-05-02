## Makecode
[마이크로소프트 Makecode](https://github.com/Microsoft/pxt)


Microsoft MakeCode는 오픈 소스 프로젝트인 Microsoft Programming Experience Toolkit (PXT)을 기반의 UI 편집기입니다.

PXT는 컴퓨터 과학 교육에 중점을 두고 초보자들에게 프로그래밍 경험을 만들어 주기위한 특수 목적의 프레임워크입니다.
PXT의 기본 프로그래밍 언어는 TypeScript의 subset(JavaScript 동적 기능 제외)입니다.

PXT 주요 특징
* 텍스트 형식에 대한 변환기와 함께 블록 기반 코드 편집기
* VS 코드를 지원하는 모나코 코드 편집기
* TypeScript에서 새 블록을 정의하는 확장성 지원
* an ARM Thumb machine code emitter
* command-line 패키지 관리

로컬호스트에서 target 수행 => [로컬호스트 수행 지침](https://makecode.com/cli)

* Command Line Tool
  * pxt : PXT의 Command Line Tool
  * 설치 : npm install -g pxt

* 작업공간 설정하기
  * 모든 pxt target(editor)는 대상 디렉토리를 작성해야 합니다.
  * 마이크로비트 에디터를 설치하기 위해 마이크로비트 디렉토리를 작성하는 방법은 다음과 같습니다.
    * mkdir microbit
    * cd microbit
    * pxt target microbit
    * pxt serve
