# 🎁 카카오 테크 캠퍼스 - 프론트엔드 카카오 선물하기 편

# 🙋🏻‍♀️ 4주차 질문

## 질문 1. 제어 컴포넌트와 비제어 컴포넌트의 차이가 무엇이고 제어 컴포넌트로 Form을 만들어야 하는 경우가 있다면 어떤 경우인지 예시와 함께 설명해주세요.

### 제어 컴포넌트

상태가 React 컴포넌트의 상태로 관리되는 컴포넌트입니다.
입력값이 React의 상태(state)에 의해 제어되며, 상태가 변경될 때 컴포넌트가 다시 렌더링됩니다.

### 비제어 컴포넌트

입력값을 React 상태로 관리하지 않고, ref를 사용하여 직접 DOM 요소에 접근합니다.

### 제어 컴포넌트로 Form을 만들어야 하는 경우

- 유효성 검사: 사용자가 입력한 데이터의 유효성을 실시간으로 검사하고 싶을 때.
- 폼 상태 관리: 폼의 입력값을 중앙에서 관리하고, 상태를 동기화해야 할 때.
- 조건부 렌더링: 입력값에 따라 UI를 동적으로 변경할 때.

## 질문 2. input type의 종류와 각각 어떤 특징을 가지고 있는지 설명해 주세요.

- text: 일반 텍스트 입력 필드입니다.
  - 특징: 자유로운 텍스트를 입력할 수 있습니다.
- password: 비밀번호 입력 필드입니다.
  - 특징: 입력한 내용이 가려져서 보이므로 비밀번호 입력에 적합합니다.
- email: 이메일 주소 입력 필드입니다.
  - 특징: 이메일 형식 검사를 지원합니다. 일부 브라우저에서 이메일 형식의 유효성을 검사합니다.
- number: 숫자 입력 필드입니다.
  - 특징: 숫자만 입력할 수 있으며, 스핀 박스(화살표)를 통해 값을 조정할 수 있습니다.
- date: 날짜 입력 필드입니다.
  - 특징: 날짜를 선택할 수 있는 날짜 선택기를 제공합니다.
- checkbox: 체크박스 입력 필드입니다.
  - 특징: 여러 옵션 중 하나 이상의 선택을 허용합니다.
- radio: 라디오 버튼 입력 필드입니다.
  - 특징: 여러 옵션 중 하나만 선택할 수 있습니다.
- file: 파일 업로드 필드입니다.
  - 특징: 파일을 선택하고 업로드할 수 있는 입력 필드입니다.
- submit: 제출 버튼입니다.
  - 특징: 폼을 제출하는 버튼입니다.
- button: 일반 버튼입니다.
  - 특징: 클릭 시 JavaScript 코드를 실행할 수 있습니다.

## 질문 3. label tag는 어떤 역할을 하며 label로 input field를 감싸면 어떻게 동작하는지 설명해 주세요.

- label 태그는 폼 필드에 대한 설명이나 이름을 제공하여 사용자가 입력 필드를 쉽게 이해할 수 있도록 도와줍니다.
- label 태그로 입력 필드를 감싸면 for 속성을 사용하지 않고도 라벨을 클릭할 때 입력 필드에 포커스가 이동합니다.

# 📝 기능 구현 목록

> UI를 chakra-ui 사용해서 구현한다.

> 상세 페이지에서 첨부된 oas.yaml 파일의 /api/v1/products/{productId}/detail, /api/v1/products/{productId}/options를 참고하여 API를 구현한다.

> React Hook Form 등의 라이브러리를 사용하지 않으며 React의 form, ref, state만 사용하여 구현한다.

## step 1

- [x] 없는 상품의 경우 메인 페이지로 연결되도록 한다.
- [x] 나에게 선물하기 버튼 클릭 시 로그인이 되어있지 않다면 로그인 페이지로 이동한다.

## step 2

- [x] 상품 상세 페이지에서 상품의 개수를 option API의 giftOrderLimit을 초과한 경우 선택이 불가하게 한다.
- [x] 결제 페이지의 Form을 validation 한다.
  - [x] 카드 메시지를 입력하지 않으면 메시지를 입력하라고 안내한다.
  - [x] 카드 메시지가 100글자가 넘어가면 100자 이내로 입력하라고 안내한다.
  - [x] 현금 영수증 checkbox 클릭 시 현금영수증 번호가 입력되었는지 확인한다.
  - [x] 현금 영수증 입력은 숫자만 입력하도록 안내한다.

## step 3

- [x] 기존에 만든 form / input을 react-hook-form으로 변경한다.
- [x] validate 또한 react-hook-form 기능을 적극적으로 활용한다. (이 과정에서 zod를 사용해도 좋다.)
