## Makecode Block 정의 [https://makecode.com/defining-blocks](https://makecode.com/defining-blocks)
<p>
 MakeCode API에 주석을 작성하여 블록 편집기에서 표시하는 방법을 설명합니다.<br>
 [playground](https://makecode.com/playground)어떻게 작동하는지 확인해보고 수정해서 새로운 것을 만들어보세요.<br>
 블록은 API 요소(export function, method, enum 등)의 시작 부분에 주석이 추가되어 정의됩니다.<br>
 속성은 //%의 주석 형식으로 시작하는 주석 행에 지정됩니다. <br>
 모든 //% 주석은 API의 코드가있는 TypeScript 라이브러리 파일에서 찾을 수 있습니다.<br>
 선택적으로 C++ 라이브러리 파일 또는 TypeScript 시뮬레이터 파일에서 자동 생성될 수 있습니다.
</p>

### 분류
최상위 TypeScript 네임 스페이스는 블록 편집기 도구 상자에서 범주를 채우는 데 사용됩니다. 이름은 도구 상자에 자동으로 대문자로 표기됩니다. 네임 스페이스에 대한 JsDoc 주석, 색상 및 가중치뿐만 아니라 알기 쉬운 이름 (유니 코드)을 제공 할 수도 있습니다. 블록의 모양과 가독성에 큰 영향을주기 때문에 신중하게 색상을 선택하는 것이 좋습니다. 동일한 네임 스페이스 내의 모든 블록은 동일한 색상을 사용하므로 사용자는 샘플에서 카테고리를 쉽게 찾을 수 있습니다.

```javascript
/**
 * Provides access to basic micro:bit functionality.
 */
//% color=190 weight=100 icon="\uf1ec" block="Basic Blocks"
namespace basic {
    ...
}
```
#### //% 
* color은 hue 값 또는 HTML 색상을 사용합니다.
* weight는 도구 상자에 범주가 표시되는 위치를 결정합니다. weight가 높을수록 맨 위에 더 가깝게 나타납니다. 
* icon은 표시할 아이콘의 유니코드 문자입니다. 시맨틱 UI 아이콘 세트는 Font Awesome (작성 당시 v4.5.6)에서 포팅되었으며 전체 목록은 [http://fontawesome.io/icons/](http://fontawesome.io/icons/)에서 찾을 수 있습니다.


#### Category groups
유사한 블록을 그룹화하여 블록 카테고리를 보다 체계적으로 구성할 수 있습니다. 그룹 기능을 사용하면 동일한 그룹의 블록이 도구 상자에 함께 표시되고 그 그룹의 레이블이 그 위에 표시됩니다. 그룹을 정의하려면 네임 스페이스에 groups 속성을 추가하십시오.groups 속성은 그룹 이름의 배열입니다. 그룹을 정의하는 순서는 그룹이 도구 상자에 표시되는 순서입니다. 명명 된 그룹에 할당되지 않은 블록은 레이블을 표시하지 않는 기본 기타 그룹에 배치됩니다. 
other 그룹은 그룹 순서대로 그룹화되지 않은 블록이 나타나는 위치를 결정하는 데 사용할 수 있습니다.블록을 그룹에 지정할 때 이름은 대소 문자를 구분하므로 블록에 넣은 그룹 이름이 그룹 정의의 그룹 이름과 동일한 지 확인하십시오.

#### 블록
//% block 속성인 exported functions은 블록 편집기에서 사용할 수 있습니다. 
```javascript
//% block
    export function helloZambit() {
        basic.showString("Zambit")
    }
```
블록의 모양을보다 세부적으로 제어해야하는 경우 blockId 및 블록 매개 변수를 지정할 수 있습니다.

* blockId는 블록에 대해 고유한 ID입니다. 이 ID는 블록 코드로 일련 번호가 지정되어 있으므로 변경하면 사용자가 손상 될 수 있습니다. 지정되지 않은 경우 네임 스페이스 및 함수 이름에서 파생되므로 함수 또는 네임 스페이스의 이름을 변경하면 TypeScript 및 Blocks 사용자가 모두 손상됩니다. 
* 블록은 블록 구조를 만들기위한 구문을 포함합니다.
