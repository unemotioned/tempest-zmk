<!-- markdownlint-disable-file MD013 -->

# ZMK 사용 방법

## 목차

- [Keyboard](#keyboard)
- [Git and Sourcetree](#git-and-sourcetree)
- [Clone Repository](#clone-repository)
- [Flash](#flash)
- [Edit Layouts](#edit-layouts)
- [Philosophy of My Layouts](#philosophy-of-my-layouts)

---

## Keyboard

`이 키보드는 영국에서 최초로 시작되어 일년에 한 바퀴 돌면서 받는 사람에게 행운을 ...`

38 keys split splayed(새끼, 약지 열이 벌어져 있음) column stagger(좌우가 아니라 위아래로 뒤틀려 있음) keyboard

- Controller: Supermini NRF52840 ([nice!nano](https://nicekeyboards.com/docs/nice-nano/) clone)
- Battery: 301230 110mAh 3.7v
- Switch: [MoEro Choc V1 Plum Blossom Silent 45g](https://www.moergo.com/collections/choc-v1-key-switches/products/kailh-choc-v1-silent-key-switches-cherry-blossom-plum-blossom-20-pack?variant=51316351467793)
- Keycaps: [DDC Profile](https://keeb.supply/products/ddc-keycaps)

왼쪽이 메인으로 오른쪽이 왼쪽에 연결되고 왼쪽이 컴퓨터랑 연결되기 때문에 왼쪽 배터리가 더 빨리 닳는다.
4 ~ 5일에 한번 30분 정도 충전하면 됨.

---

## Git and Sourcetree

- [git](https://git-scm.com/install/windows) 설치
- [sourcetree](https://www.sourcetreeapp.com/) 설치

---

## Clone Repository

- 이 [리포지토리](https://github.com/unemotioned/tempest-zmk) 클론
- .git/ 폴더 삭제하고 git init 해서 본인 github 계정 리포지토리로 올리기
- enable github action

---

## Flash

---

## Edit Layouts

---

## Philosophy of My Layouts

`"I use Vim by the way."`

### Base

`Home row mods` 순서는 Windows, Control, Shift, Alt 순서.
잘쓰지 않는 Windows를 새끼 손가락 Shfit는 강한 중지에 위치.
검지에 위치 시킬수도 있으나 검지는 키를 6개 눌러야 하기 때문에 중지에 두는것이 더 유연함.
그리고 Shift가 Control과 Alt 사이에 있으면 단축키를 누를때도 더 쉬움.
자세한거는 [A guide to home row mods](https://precondition.github.io/home-row-mods) 참고.
타자를 칠때 modifiers랑 계속 오타가 난다면 [urob/timeless homerowmods](https://github.com/urob/zmk-config#timeless-homerow-mods) 참고.

Hold Tap으로 지정된 키 &hrm_l, &hrm_r, &lt, &mt 등의 키를 연속적으로 입력할려면 `quick-tap-ms`의 값 170ms 안에 두번 누르면 됨.

`&mt shift bspc`의 경우 글을 지우고서 바로 shift키를 누르고서 입력해야 하는 경우 bspc가 연속으로 입력될수 있음.
`quick-tap-ms`를 더 줄이면 더블탭해서 연속 입력하기가 힘들어질 수 있음.
170ms는 제가 적당한 값을 찾아서 쓰는거기 때문에 위와같은 상황이 있으면 적당히 기다렸다가 Shift를 누르는게 나을듯.

Cut, Copy, Paste, Undo [콤보](https://zmk.dev/docs/keymaps/combos)를 왼쪽 R4에 배치 했는데 그러면 오른손으로 마우스를 조작하면서 복사 붙여넣기등을 하기가 편하다. 왼손에 bspc, enter 키가 있는것도 비슷한 이유.

- 작은 따옴표(') 콤보: 36키 레이아웃에서 쓰기 때문에 추가했는데 손목을 밖으로 구부리지 않아도 되서 생각보다 편하다.
- 마이너스(dash) 콤보: `SCREAM_SNAKE_CASE`를 입력할때 base와 symb 레이어를 왔다갔다 하기 않기 위해.
- youtube_speed_down/up 콤보: 유튜브에서 &lt;, &gt;를 이용해서 배속 조절이 가능한데 그걸 4번 알아서 해주는 Macro를 먼저 지정하고 사용.

> NOTE: 콤보와 Homerowmods가 겹치는 키를 여러게 누를때(ex: Ctrl + Shift + P) 동시에 누르면 콤보가 나가기 때문에 `timeout-ms` 값 35ms 보다 긴 간격을 두고서 눌러야 한다.

### Symb

`왼손 엄지 안쪽 키`를 press and hold.

숫자열에 있는 모든키를 때려박음. Layer 1 키와 Shift 키를 누르는 엄지가 겹치기 때문에 쉬프트를 눌렀을때 사용한 문자들도 같이 나열함.
`온점`은 Base와 같은 위치를 쓰기해서 &trans로 했고 `반점`은 어디 둘지 몰라서 그냥 남는 자리에다가 위치.

`&lt; &gt;` 콤보: 엄지를 &lt와 쉬프트키를 왔다갔다 하는게 귀찮아서 Symb 레이어에서만 사용가능 하도록 설정.

### Arrw

`오른손 엄지 안쪽 키`를 press and hold.

화살표키 Left, Down, Up, Right가 H, J, K, L키 위치에 있음.
`Vim motion`과 똑같이 하기 위해서 그리고 위아래로 비슷하게 `Navigation` 키와 `Media` 키를 배치.

### Util

`왼손, 오른손 엄지 안쪽 키`를 동시에 press and hold. `Conditional Layers`를 사용하는것보다 이 방식이 더 잘됨.

블루투스 연결된 기기를 0 ~ 3 선택가능. 선택한 기기 연결 지우는 `&bt_clr`는 헷갈리지 않게 왼쪽으로 분리.
`print screen`과 `&my_email` 매크로를 배치.

왼쪽은 아무것도 지정하지 않았는데 저는 IDE나 VSCode 단축키등을 해놨었습니다. 복잡하게 쉬프트, 컨트롤, 알트를 누르는것보다 자주쓰는거를 한곳에 모아놓는게 괜찮았습니다.

### Boot

각 키보드의 안쪽, 중간 엄지키를 순서대로 누름.

일반적으로 사용할때는 눌리지 않도록 엄지키 두개를 동시에 누르고 `T`또는 `Y`키를 눌러야 `boot loader` 모드 진입.
리셋 버튼을 누르는것보다 쉬움.

- `사용방법`: 왼쪽 예시
  1. 키보드를 컴퓨터랑 USB로 연결
  2. 왼쪽 안쪽 엄지키를 press and hold
  3. 왼쪽 중간 엄지키를 press and hold
  4. T키에 위치한 `&boot_loader`키 누름

> NOTE: ZMK 키보드는 무선이라 연결되지 않은 상태에서도 boot loader 모드로 들어갈 수 있다. 그땐 껐다 키면 됨.

### Numb

`C`키 press and hold.

`Symb` 레이어에서 숫자 치는거는 뭔가 아직도 완전히 익숙하지 않아서 계산기 형태로 만듦.

---

#### Happy Typing 🎉
