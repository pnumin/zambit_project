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
+ GitHub 계정에 확장 기능을 만들 repository를 생성합니다. (pxt-xxx)
+ 계정을 만들었으면 MakeCode 웹 앱을 계정에 연결해야합니다.
+ 이를 수행하려면 pxt serve를 실행해서 microbit Makecode에서 새 프로젝트를 열고 상단의 기어 휠 메뉴로 이동 한 다음 확장프로그램을 선택하십시오.
+ 하단에 GitHub에 로그인 링크를 누릅니다. 링크가 없다면 /beta 버전을 사용합니다.
+ GitHub 토큰을 생성하라는 대화 상자가 나타납니다. 토큰을 대화 상자에 붙여 넣으십시오. 
+ 사용하는 각 편집기 (micro:bit, Circuit Playground 등)에 대해 토큰을 다시 붙여 넣어야하지만, 모두 동일한 토큰을 사용할 수 있습니다.
+ microbit Makecode 홈 화면으로 돌아갑니다.
+ 홈화면 대화 상자에는 GitHub 저장소가 나열되며 새 저장소를 만들 수있는 추가 옵션이 있습니다.<br>
(또한 URL 가져 오기 옵션은 이제 목록 (특히 조직 리포지토리)에서 리포지토리를 찾을 수 없거나 목록을 더 빨리 검색하는 방법으로 유용한 https : //github.com / ... URL을 지원합니다. URL의 복사 / 붙여 넣기를 사용합니다.)
+ 완전히 비어있는 저장소를 가져 오거나 새로 만든 저장소를 만들면 MakeCode가 pxt.json 및 기타 지원 파일을 사용하여 자동으로 초기화합니다.
+ pxt.json 파일을 사용하지 않고 비어 있지 않은 저장소를 가져 오는 경우 초기화 할 것인지 묻는 메시지가 나타납니다. 이 경우 기존 파일을 덮어 쓸 수 있습니다.
+ 현재 기존 프로젝트를 GitHub에 푸시 할 수있는 방법은 없습니다. 이 문제를 해결하려면 새 프로젝트를 만들고 main.ts 파일의 내용을 복사하여 붙여 넣으십시오.
 
#### Commit and push
+ repo 설정이 완료되면 파일을 편집하십시오.
+ 변경이 되면 왼쪽 하단의 탐색기의 상단에 GitHub 동기화 버튼을 사용하여 GitHub에 푸시합니다.<br>
  변경 내용이 존재하면, 커밋을 생성하고, GitHub에서 최신 변경 사항을 가져오고, 필요한 경우 커밋을 병합 또는 fast-forward하고 결과를 GitHub로 푸시합니다.<br>
  변경된 내용이 있으면 커밋 메시지를 작성합니다. <br>변경 사항을 설명 할 때 버전 번호를 지정하는 옵션도 제공됩니다.<br>
  확장 프로그램을 처음 참조 할 때 최신 범프 버전이 사용됩니다. <br> 
  마찬가지로, 새로운 버전이있는 경우 확장 옆에 약간의 업그레이드 버튼이 나타납니다.<br>
  실제로 ommit, push, pull 구별하는 것은 없고 모두 동기화 작업에서 동시에 발생합니다.<br>
  프로젝트 설정 페이지의 버전 번호 링크를 따라 변경 기록을 볼 수 있습니다.
+ 동기화 버튼 옆에 추가 버튼을 사용하여 새파일을 추가할 수 있습니다.<br>
프로젝트를 조직화하는 데 사용됩니다. <br>
TypeScript 컴파일러의 경우 큰 파일 하나를 사용하든 작은 파일들을 사용하든 상관없습니다.

#### Conflicts
+ 여러 사람이 같은 확장 프로그램을 동시에 편집하면서 편집 충돌이 발생할 수 있습니다. <br>
동일한 사람이 여러 컴퓨터, 브라우저 또는 웹 사이트를 사용하여 확장 프로그램을 편집하는 상황과 유사합니다.
+ 일반적으로 두 사람이 동일한 버전의 GitHub extension을 동기화한 다음 두 사람이 모두 편집합니다.<br>
첫 번째 사람이 변경 사항을 성공적으로 푸시합니다.<br>
MakeCode가 두 번째 사람의 변경 사항을 푸시하려고하면, 현재 버전이 아닌 버전에 대한 변경 사항임을 알게됩니다.<br>
이전 버전을 기반으로 커밋을 만들고 표준 git merge (GitHub의 서버 측 실행)을 사용하려고합니다.<br>
두 사람이 서로 다른 파일을 편집하거나 파일의 다른 부분을 편집하면이 작업이 일반적으로 성공합니다. 두 작업을 논리적으로 결합한 결과로 끝납니다.
이 경우 사용자 상호 작용이 필요하지 않습니다.

#### Testing your extension
+ 확장 프로그램의 블록을 테스트하려면 홈 화면에서 새 프로젝트 버튼을 누르고 확장 대화 상자로 이동하십시오. <br>
추가로 사용할 수있는 모든 GitHub 프로젝트를 나열합니다. 확장 프로그램을 선택하고 블록이 어떻게 보이는지 확인하십시오.<br>
TypeScript API를 테스트 할 때는 별도의 프로젝트가 필요하지 않으며 대신 확장 자체에서 test.ts 파일을 사용할 수 있습니다. 확장을 프로젝트에 직접 추가 할 때가 아니라 확장을 직접 실행할 때만 사용됩니다. TypeScript 테스트 코드를 넣을 수 있습니다.

#### Non-extensions
+ GitHub 기능은 확장 기능에만 국한되지 않습니다. 다른 MakeCode 프로젝트를 저장할 때도 사용할 수 있습니다. 여러 사람과 함께 프로젝트를 공동 작업 할 때도 사용할 수 있습니다. 현재 모든 GitHub 프로젝트가 Extensions 대화 상자에 표시됩니다.

