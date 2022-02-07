# CSS 레이아웃

## Float

박스를 왼쪽 혹은 오른쪽으로 이동시켜 텍스트를 포람 인라인 요소들이 주변을 wrapping 하도록 함

요소가 Normal flow를 벗어나도록 함

속성 - none(기본값), left, right

### Flexbox

행과 열 형태로 아이템을 배치하는 1차원 레이아웃 모델

Flexbox축

`justify-content : ` 요소들을 가로선 상에서 정렬

- `flex-start`: 요소들을 컨테이너의 왼쪽으로 정렬합니다.
- `flex-end`: 요소들을 컨테이너의 오른쪽으로 정렬합니다.
- `center`: 요소들을 컨테이너의 가운데로 정렬합니다.
- `space-between`: 요소들 사이에 동일한 간격을 둡니다.
- `space-around`: 요소들 주위에 동일한 간격을 둡니다.

`align-items: ` 요소들을 세로선 상에서 정렬

- `flex-start`: 요소들을 컨테이너의 꼭대기로 정렬합니다.
- `flex-end`: 요소들을 컨테이너의 바닥으로 정렬합니다.
- `center`: 요소들을 컨테이너의 세로선 상의 가운데로 정렬합니다.
- `baseline`: 요소들을 컨테이너의 시작 위치에 정렬합니다.
- `stretch`: 요소들을 컨테이너에 맞도록 늘립니다.

`flex-direction :`  컨테이너 안에서 요소들이 정렬해야 할 방향을 지정

- `row`: 요소들을 텍스트의 방향과 동일하게 정렬합니다.
- `row-reverse`: 요소들을 텍스트의 반대 방향으로 정렬합니다.
- `column`: 요소들을 위에서 아래로 정렬합니다.
- `column-reverse`: 요소들을 아래에서 위로 정렬합니다.

`order` 요소 순서 바꾸기, 기본값 : 0, 양수나 음수로 바꿀 수 있음

`align-self`는 개별 요소에 적용할 수 있는 속성,  `align-items`가 사용하는 값들을 인자로 받으며, 그 값들은 지정한 요소에만 적용됩니다.

`flex-wrap :`  줄 바꿈 지정

- `nowrap`: 모든 요소들을 한 줄에 정렬합니다.
- `wrap`: 요소들을 여러 줄에 걸쳐 정렬합니다.
- `wrap-reverse`: 요소들을 여러 줄에 걸쳐 반대로 정렬합니다.

`flex-flow` :  `flex-direction` `flex-wrap`

`align-content:`여러 줄 사이의 간격을 지정

- `flex-start`: 여러 줄들을 컨테이너의 꼭대기에 정렬합니다.
- `flex-end`: 여러 줄들을 컨테이너의 바닥에 정렬합니다.
- `center`: 여러 줄들을 세로선 상의 가운데에 정렬합니다.
- `space-between`: 여러 줄들 사이에 동일한 간격을 둡니다.
- `space-around`: 여러 줄들 주위에 동일한 간격을 둡니다.
- `stretch`: 여러 줄들을 컨테이너에 맞도록 늘립니다.