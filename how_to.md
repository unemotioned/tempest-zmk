<!-- markdownlint-disable-file MD013 -->

# 사용방법

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

- **Controller:** Supermini NRF52840 ([nice!nano](https://nicekeyboards.com/docs/nice-nano/) clone)
- **Battery:** 301230 110mAh 3.7v
- **Switch:** [MoEro Choc V1 Plum Blossom Silent 45g](https://www.moergo.com/collections/choc-v1-key-switches/products/kailh-choc-v1-silent-key-switches-cherry-blossom-plum-blossom-20-pack?variant=51316351467793)
- **Keycaps:** [DDC Profile](https://keeb.supply/products/ddc-keycaps)

왼쪽이 메인으로 오른쪽이 왼쪽에 연결되고 왼쪽이 컴퓨터랑 연결되기 때문에 왼쪽 배터리가 더 빨리 닳는다.
4~5일에 한번 30분 정도 충전하면 됨.

컨트롤러 테두리는 보기 좋게 검게 칠함.

---

## Git and Sourcetree

- [git](https://git-scm.com/install/windows) 설치
- [sourcetree](https://www.sourcetreeapp.com/) 설치 (mercury, bitbucket 등의
설정은 넘겨도 된다)

---

## Clone Repository

1. 리포지토리와 똑같은 폴더를 하나 만들고 이 [리포지토리](https://github.com/unemotioned/tempest-zmk)를 클론
2. `.git` 폴더 삭제하고 `git init` 해서 본인 깃허브 리포지토리로 올리기
3. GitHub의 리포 페이지에서 action 활성화

---

## Flash

### Local Build

[unemotioned charybdis-zmk](https://github.com/unemotioned/charybdis-zmk) 참고

---

## Edit Layouts

### [nickoutsos keymap editor](https://nickcoutsos.github.io/keymap-editor/)

깃허브에서 리포를 추가하고서 몇 분 기다려야한다.

### [kit-314 customkeymap](https://customkeymap.com/)

모든 레이아웃과 combos, macros, behaviors를 전부 한 페이지에서 보여줌.

깃허브 계정의 `{이름/리포이름}`을 입력.

## Edit Combos

[Combos](https://zmk.dev/docs/keymaps/combos): 두개 이상의 키를 동시에 눌러서 다른 동작으로 하도록 하는것.

[Keymap Editor](https://nickcoutsos.github.io/keymap-editor/) 사이트의
`Combos` 탭에서 만든다.

- `timeout-ms`: 지정한 시간 안에 눌러야 콤보로 인식
- `require-prior-idle-ms`: 일반적으로 타자를 치다가 지정한 시간 만큼 후에 눌러야 콤보로 인식 &rarr; 오타 줄임
- `slow-release`: 콤보 키를 눌렀다가 때야 입력이 된다
- `layers`: 어떤 레이어에서 동작을 할지(값이 없으면 모든 레이어에서 동작)

---

## Philosophy of My Layouts

`"I use Neovim by the way."`

참고할만한 다른 레이아웃: [miryoku](https://github.com/manna-harbour/miryoku)

`Keymap Editor`에서 보기 좋게 레이어 이름은 4글자로 통일 했다.

### 0. Base

`Home row mods` 순서는 Windows, Control, Shift, Alt 순서.
잘 쓰지 않는 Windows를 새끼 손가락 Shift는 강한 중지에 위치.
검지에 위치 시킬 수도 있으나 검지는 키를 6개 눌러야 하기 때문에 중지에 두는것이 더 유연함.
그리고 Shift가 Control과 Alt 사이에 있으면 단축키를 누를때도 더 쉬움.
자세한거는 [A guide to home row mods](https://precondition.github.io/home-row-mods) 참고.
타자를 칠 때 modifiers랑 계속 오타가 난다면 [urob/timeless homerowmods](https://github.com/urob/zmk-config#timeless-homerow-mods) 참고.

Hold Tap으로 지정된 키 `&hrm_l`, `&hrm_r`, `&lt`, `&mt` 등의 키를 연속적으로 입력할려면 `quick-tap-ms`의 값 170ms 안에 두번 누르면 됨.

`&mt shift bspc`의 경우 글을 지우고서 바로 shift키를 누르고서 입력해야 하는 경우 bspc가 연속으로 입력될 수 있음.
`quick-tap-ms`를 더 줄이면 더블탭해서 연속 입력하기가 힘들어질 수 있음.
170ms는 제가 적당한 값을 찾아서 쓰는거기 때문에 위와같은 상황이 있으면 적당히 기다렸다가 Shift를 누르는게 나을듯.

Cut, Copy, Paste, Undo [콤보](https://zmk.dev/docs/keymaps/combos)를 왼쪽 R4에 배치했는데 그러면 오른손으로 마우스를 조작하면서 복사 붙여넣기등을 하기가 편하다. 왼손에 bspc, enter 키가 있는 것 도 비슷한 이유.

- 작은 따옴표(`'`) 콤보: 36키 레이아웃에서 쓰기 때문에 추가했는데 손목을 밖으로 구부리지 않아도 돼서 생각보다 편하다.
- 마이너스(dash) 콤보: `SCREAM_SNAKE_CASE`를 입력할때 base와 symb 레이어를 왔다갔다 하기 않기 위해.
- youtube_speed_up/down 콤보: 유튜브에서 `<`, `>`를 이용해서 배속 조절이 가능한데 그걸 4번 알아서 해주는 Macro를 먼저 지정하고 사용.

> [!NOTE]
> 콤보와 Homerowmods가 겹치는 키를 여러 개 누를 때(ex: Ctrl + Shift + P) 동시에 누르면 콤보가 나가기 때문에 `timeout-ms` 값 35ms 보다 긴 간격을 두고서 눌러야 한다.

### 1. Symb

`왼손 엄지 안쪽 키`를 press and hold.

숫자열에 있는 모든 키를 때려박음. Layer 1 키와 Shift 키를 누르는 엄지가 겹치기 때문에 쉬프트를 눌렀을때 사용한 문자들도 같이 나열함.
`온점`은 Base와 같은 위치를 쓰기해서 `&trans`로 했고 `반점`은 어디 둘지 몰라서 그냥 남는 자리에다가 뒸음.

`<`, `>` 콤보: 엄지를 `<`와 쉬프트키를 왔다갔다 하는게 귀찮아서 Symb 레이어에서만 사용가능 하도록 설정.

### 2. Arrw

`오른손 엄지 안쪽 키`를 press and hold.

화살표키 Left, Down, Up, Right가 H, J, K, L키 위치에 있음.
`Vim motion`과 똑같이 하기 위해서 그리고 위아래로 비슷하게 `Navigation` 키와 `Media` 키를 배치.

### 3. Util

`왼손, 오른손 엄지 안쪽 키`를 동시에 press and hold. `Conditional Layers`를 사용하는 것보다 이 방식이 더 잘됨.

블루투스 연결된 기기를 0~3 선택가능. 선택한 기기 연결 지우는 `&bt_clr`는 헷갈리지 않게 왼쪽으로 분리.
`print screen`과 `&my_email` 매크로를 배치.

왼쪽은 아무것도 지정하지 않았는데 복잡한 쉬프트, 컨트롤, 알트를 사용하는 IDE 단축키를 누르는것보다 자주쓰는거를 한곳에 모아놓는게 괜찮은듯.

### 4. Boot

각 키보드의 안쪽, 중간 엄지 키를 순서대로 누름.

일반적으로 사용할 때는 눌리지 않도록 엄지키 두개를 동시에 누르고 `T` 또는 `Y`키를 눌러야 `boot loader` 모드 진입.
리셋 버튼을 누르는 것보다 쉬움.

> [!NOTE]
> ZMK 키보드는 무선이라 연결되지 않은 상태에서도 boot loader 모드로 들어갈 수 있다. 그땐 껐다 키면 됨.

#### Boot Procedure

`사용방법` - 왼쪽 예시:

1. 키보드를 컴퓨터랑 USB로 연결
2. 왼쪽 안쪽 엄지키를 press and hold
3. 왼쪽 중간 엄지키를 press and hold
4. T키에 위치한 `&boot_loader`키 누름

### 5. Numb

`C`키 press and hold.

`Symb` 레이어에서 숫자 치는 거는 뭔가 아직도 완전히 익숙하지 않아서 계산기 형태로 만듦.

---

#### Happy Typing 🎉
