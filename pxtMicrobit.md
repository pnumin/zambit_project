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
makecode <br>
 L pxt      
 L pxt-common-packages  
 L pxt-microbit
 
 ### 로컬 호스트에서 실행
 pxt serve
  * cpp 파일을 수정해야 할 필요가있는 경우 --localbuild 플래그를 사용하여 컴파일 : pxt serve --local
  * 빌드속도를 높이려면 rebundle 옵션 사용 : pxt serve --rebundle
 
 ### Cleaning
 pxt clean

## Developing new extensions 
새로운 확장 기능의 제작 및 테스트는 웹 편집기에서 직접 수행 할 수 있습니다.<br>
참고문서 => [https://makecode.com/blog/github-packages](https://makecode.com/blog/github-packages)
<p>
 MakeCode는 중학생을 대상으로하는 쉬운 수준의 입력이 가능한 플랫폼이지만 TypeScript로 프로그램을 작성하는 고급 사용자는 무한한 독창성과 복잡성을 사용할 수 있습니다.<br>
TypeScript의 하위 집합은 TypeScript의 일반적인 언어 기능 대부분을 지원하지만 micro : bit와 같이 매우 제한된 리소스를 사용하여 효율적으로 컴파일 할 수 있습니다.<br>
 Makecode의 런타임 라이브러리는 대부분의 정의된 모든 블록을 포함하여 정적 typescript로 구현됩니다. 
또한 모든 기능을 갖춘 모나코 텍스트 편집기를 포함합니다.
</p>
<p>
처음부터 GitHub에서 호스팅하는 사용자가 제공하는 패키지로 확장을 할 수 있도록 하였다. 이러한 패키지는 makecode에서 자체 사용자 인터페이스를 도입 할 수 있습니다. 패키지는 먼저 검색을 위해 승인을 받아야하지만, 불법적이지 않으면 정확한 URL을 제공하여 승인없이도 로드 할 수 있습니다.
</p>
<p>
지금까지는 패키지 제작에 커맨드 라인 툴 (npm과 git, 필요한 npm 패키지)을 사용해야했기 때문에 패키지 작성자에게 상당한 장애가 될 수 있었습니다.<br>다양한 편집기에서 기능을 사용할 수 있게 됨에 따라 command line이나 다른 툴을 설치하지 않고도 웹앱에서 직접 패키지를 만들어  GitHub에 게시할 수 있습니다.
</p>

### GitHub extension 제작
참고문서 => [https://makecode.com/extensions/github-authoring](https://makecode.com/extensions/github-authoring)<br>
MakeCode의 시작부터 GitHub에서 호스팅되는 사용자 확장 기능을 사용하여 편집기를 확장하는 기능이 제공되었습니다.<br>
이러한 확장기능은 makecode에서 자신의 UI를 넣을 수 있다. <br>
확장기능은먼저 검색을 위해 승인을 받아야하지만, 불법적이지 않으면 정확한 URL을 제공하여 승인없이도 로드 할 수 있습니다.<br>
지금까지는 패키지 제작에 커맨드 라인 툴 (npm과 git, 필요한 npm 패키지)을 사용해야했기 때문에 패키지 작성자에게 상당한 장애가 될 수 있었습니다.<br>다양한 편집기에서 기능을 사용할 수 있게 됨에 따라 command line이나 다른 툴을 설치하지 않고도 웹앱에서 직접 패키지를 만들어  GitHub에 게시할 수 있습니다.

#### GitHub account and repo
+ 먼저 아직 GitHub 계정이 없으면 GitHub 계정이 필요합니다.
+ 계정을 만들었으면 MakeCode 웹 앱을 계정에 연결해야합니다.
+ 이를 수행하려면 Makecode에서 새 프로젝트를 열고 상단의 기어 휠 메뉴로 이동 한 다음 확장프로그램을 선택하십시오.
+ 하단에 GitHub에 로그인 링크를 누릅니다. 링크가 없다면 /beta 버전을 사용합니다.
+ GitHub 토큰을 생성하라는 대화 상자가 나타납니다. 토큰을 대화 상자에 붙여 넣으십시오. 
+ 사용하는 각 편집기 (micro:bit, Circuit Playground 등)에 대해 토큰을 다시 붙여 넣어야하지만, 모두 동일한 토큰을 사용할 수 있습니다.
+ 로그인하면 홈 화면으로 돌아갑니다.
+ import 버튼을 누른 후에 나타나는 대화 상자에는 GitHub 저장소를 나열하거나 새 저장소를 만들 수있는 추가 옵션이 있습니다.<br>
(또한 URL 가져 오기 옵션은 이제 목록 (특히 조직 리포지토리)에서 리포지토리를 찾을 수 없거나 목록을 더 빨리 검색하는 방법으로 유용한 https : //github.com / ... URL을 지원합니다. URL의 복사 / 붙여 넣기를 사용합니다.)
+ 완전히 비어있는 저장소를 가져 오거나 새로 만든 저장소를 만들면 MakeCode가 pxt.json 및 기타 지원 파일을 사용하여 자동으로 초기화합니다.
+ pxt.json 파일을 사용하지 않고 비어 있지 않은 저장소를 가져 오는 경우 초기화 할 것인지 묻는 메시지가 나타납니다. 이 경우 기존 파일을 덮어 쓸 수 있습니다.
+ 현재 기존 프로젝트를 GitHub에 푸시 할 수있는 방법은 없습니다. 이 문제를 해결하려면 새 프로젝트를 만들고 main.ts 파일의 내용을 복사하여 붙여 넣으십시오.
 
