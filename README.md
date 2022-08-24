# Bootstrap-test

## Bootstrap개요
- 부트스트랩(Bootstrap)은 웹사이트를 쉽게 만들 수 있게 도와주는 HTML, CSS, JS 프레임워크이다. 하나의 CSS로 휴대폰, 태블릿, 데스크탑까지 다양한 기기에서 작동한다. 다양한 기능을 제공하여 사용자가 쉽게 웹사이트를 제작, 유지, 보수할 수 있도록 도와준다.

## CDN으로 사용하기
- 우리 프로젝트에서 부트스트랩을 사용할수 잇는 방법에는 여러가지가 잇지만 우선 CDN으로 사용하는 방법에 대해서 알아보면
- 부트스트랩은 HTML과 CSS와 JS의 프레임 워크이기 때문에, 클래스 이름과 id 이름 등으로 구분을 하여 그에 맞게 동작을 하게 되어 잇다. 그렇기 때문에 CSS,JS에 대한 코드 패키지를 컴퓨터 에게 알려줘야 하는데 그것을 link태그와 , script태그를 통해서 연결할수 잇다.
- 우선 CSS코드를 가져오고, JS코드를 사용할때는 두가지 방법이 잇다.
  1. bundle을 이용한 방법 - 이방법은 Bootstrap은 기본적으로 popper라는 패키지를 이용하기 때문에 popper와 현재 bootstrap의 JS기술을 합친 방법으로 만약 npm에서 popper를 설치 하지 않았거나, 부트스트랩에서 드롭다운과 같은 메뉴를 사용하고 싶다면 bundle을 설치해줘야하고
  1. seperatly - 분리 방법, 즉 pooper와 분리해서 사용한다는 의미인데, 그 의미는 이미 popper에 패키지를 가지고 잇거나, 아니면 드롭다운과 같은 메뉴를 사용하지 않을때 사용하면 좀더 bootstrap을 가볍게 사용할수 잇다라는 장점을 가지고 잇다.

## 버튼그룹
```html
<div class="btn-group">
    <button type="button" class="btn btn-primary btn-lg">Primary</button>
    <button type="button" class="btn btn-outline-secondary">Secondary</button>
    <button type="button" class="btn btn-success btn-sm">Success</button>
    <div class="btn btn-outline-primary">ABC</div>
</div>
```

## 드롭다운과 리스트
```html
  <ul class="list-group">
    <li class="list-group-item-action">An item</li>
    <li class="list-group-item active">A second item</li>
    <li class="list-group-item">A third item</li>
    <li class="list-group-item">A fourth item</li>
    <li class="list-group-item">And a fifth one</li>
  </ul>
```
## 양식
- form과 관련된 양식을 사용할때도 여러가지 템플릿이 잇기에 유용하게 사용할수 잇다.

## 모달
```html
  <!-- Button trigger modal -->
  <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
    Launch demo modal
  </button>

  <!-- Modal -->
  <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <form>
            <div class="mb-3">
              <label for="exampleInputEmail1" class="form-label">Email address</label>
              <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
              <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>
            </div>
            <div class="mb-3">
              <label for="exampleInputPassword1" class="form-label">Password</label>
              <input type="password" class="form-control" id="exampleInputPassword1">
            </div>
            <div class="mb-3 form-check">
              <input type="checkbox" class="form-check-input" id="exampleCheck1">
              <label class="form-check-label" for="exampleCheck1">Check me out</label>
            </div>
          </form>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
          <button type="submit" class="btn btn-primary">Submit</button>
        </div>
      </div>
    </div>
  </div>
```
``` JS
console.log('test')

const emailInputEl = document.querySelector('#exampleInputEmail1')
const modalEl = document.querySelector('#exampleModal')

modalEl.addEventListener('shown.bs.modal', function() {
  emailInputEl.focus()
})
```
## 툴팁
- Tooltips are opt-in for performance reasons, so you must initialize them yourself.
``` html
  <button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="top" data-bs-title="Tooltip on top">
    Tooltip on top
  </button>
  <button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="right" data-bs-title="Tooltip on right">
    Tooltip on right
  </button>
  <button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="bottom" data-bs-title="Tooltip on bottom">
    Tooltip on bottom
  </button>
  <button type="button" class="btn btn-secondary" data-bs-toggle="tooltip" data-bs-placement="left" data-bs-title="Tooltip on left">
    Tooltip on left
  </button>
```
``` js
const tooltipTriggerList = document.querySelectorAll('[data-bs-toggle="tooltip"]')
const tooltipList = [...tooltipTriggerList].map(tooltipTriggerEl => new bootstrap.Tooltip(tooltipTriggerEl))
```

## npm프로젝트 생성
- CDN과 차이 잇게 장점이란, 부트스트랩에서 필요로 하는 기능만 가져 올수 잇고, 부트스트랩에서 기본적으로 제공하는 테마들을 우리에게 맞게 커스터 마이징도 가능하다.
1. npm프로젝트 초기화 하기
1. npm i bootstrap@5.2.0
1. JS에서 import를 통해 node_modules에 설치된 bootstrap.js 패키지 가져오기
1. SCSS에서 import를 통해 node_modules에 설치된 bootstrap.scss 패키지 가져오기

## 테마색상 커스터 마이징
- CDN방식으로는 우리가 원하는 데로 커스터 마이징 하기가 어렵다.
- customize메뉴를 통해서 사용법을 익힐수 잇다. 
```scss
// scss에서는 상대 경로를 통해서찾아야 한다. js는 node_modules로 바로 접근 가능하다
@import "../node_modules/bootstrap/scss/functions";
@import "../node_modules/bootstrap/scss/variables";
@import "../node_modules/bootstrap/scss/mixins";



// variables라는 변수 파일에서 가져온다.
$theme-colors: (
  "primary":    $primary,
  "secondary":  yellowgreen,
  "success":    $success,
  "info":       $info,
  "warning":    $warning,
  "danger":     $danger,
  "light":      $light,
  "dark":       $dark
);
```

## 성능최적화(트리 쉐이킹)
- 우리가 필요로 하는 기능만 가져다가 사용하기
- default export이기 때문에 이름으로 받아줘야한다.
- npm i @popperjs/core를 설치해서 우리가 popper를 사용하는 bootstrap을 사용한다면 이 패키지를 설치해줘야한다.
- 초기화를 하지 않아도 되는 컴포넌트도 존재하고, 초기화를 해야하는 것도 존재한다, 예를들어 스피너와 버튼같은 경우는 초기화 할필요가 없다.