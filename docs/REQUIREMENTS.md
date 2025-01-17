<h1 align="middle">🎱</h1>
<h2 align="middle">level1 - 행운의 로또</h2>
<p align="middle">자바스크립트로 구현 하는 로또 어플리케이션</p>

## 기능요구사항
- [x] 로또 구입 금액을 입력한다
  - [x] 구입 금액 유효성 검증
    - [x] 1000원 단위인지 확인
    - [x] 최소 구매 금액은 1000원, 최댓값은 NUMBER.MAX_~~~를 사용한다
  - [x] 유효하지 않은 값 입력 시 메시지 출력 후 재입력
- [x] 개수만큼 로또를 생성한다
  - [x] 구입 금액에 따라 로또 사는 개수 계산 (1000원에 한 장)
  - [x] 로또를 생성한다
    - [x] 로또 번호는 6개이다
    - [x] 로또 번호는 정수이다
    - [x] 로또 번호는 1 ~ 45 사이의 정수이다
    - [x] 한 로또 안에서 같은 값을 중복해서 뽑을 수 없다
    - [x] 오름차순으로 로또 숫자를 정렬한다
- [x] 당첨 번호와 보너스 번호를 입력받는다
  - [x] 당첨번호는 6개이다
  - [x] 로또 번호는 정수이다
  - [x] 당첨번호와 보너스 번호는 1~45 사이의 정수이다
  - [x] 모든 번호들은 중복될 수 없다
  - [x] 유효하지 않은 값 입력 시 메시지 출력 후 재입력
- [x] 당첨 내역을 계산한다
  - [x] 로또들의 당첨 등수를 계산한다
  - [x] 당첨 등수를 바탕으로 수익률을 계산한다
  - [x] 당첨 기준과 당첨 금액은 아래와 같다
    - 1등: 6개 번호 일치 / 2,000,000,000원
    - 2등: 5개 번호 + 보너스 번호 일치 / 30,000,000원
    - 3등: 5개 번호 일치 / 1,500,000원
    - 4등: 4개 번호 일치 / 50,000원
    - 5등: 3개 번호 일치 / 5,000원
- [x] 당첨 내역(수익률, 당첨 개수)을 출력한다
- [x] 게임 종료 시 재시작 여부를 입력받는다. (y: 재시작, n: 종료)
  - [x] 정해진 키워드 외의 입력값을 예외 처리한다.
  - [x] 유효하지 않은 값 입력 시 메시지 출력 후 재입력

## 프로그래밍 요구사항
- [v] 함수(또는 메서드)의 길이가 10라인을 넘어가지 않도록 구현한다.
- [x] 함수(또는 메서드)가 한 가지 일만 하도록 만든다.
- [x] 함수(또는 메서드)의 들여쓰기 depth는 1단계까지만 허용한다.
- [x] 프리코스 때 사용한 @woowacourse/mission-utils 라이브러리 사용을 금지한다.
- [x] 입출력(readline)과 관련된 테스트는 작성하지 않는다.
- [x] 도메인 로직과 UI 로직을 분리한다.
- [x] 모든 도메인 로직에 단위 테스트를 구현한다. (UI 로직은 제외)
- [x] 예측 가능하고, 실수를 방지할 수 있는 코드를 작성하기 위해 노력한다.
- [x] 함수의 매개변수는 2개 이하여야 한다.
- [x] 함수에서 부수 효과를 분리하고, 가능한 순수 함수를 많이 활용한다.
- [x] 모든 기능을 TDD로 구현하는 것을 시도하여, 테스트 할 수 있는 도메인 로직에 대해서는 모두 단위 테스트가 존재해야 한다. (단, UI 로직은 제외)

---

1단계
모듈화와 객체 간에 로직을 재사용하는 방법에 대해 고민한다.

- [x] 로또 번호와 당첨 로또 번호의 유효성 검사시 발생하는 중복 코드를 제거해야 한다.
- [x] 클래스(또는 객체)를 사용하는 경우, 프로퍼티를 외부에서 직접 꺼내지 않는다. 객체에 메시지를 보내도록 한다.
- [x] 클래스를 사용하는 경우, 3개 이상의 인스턴스 변수를 가진 클래스를 쓰지 않는다.

## 실행 예시
``` 
> 구입금액을 입력해 주세요.8000
8개를 구매했습니다.
[8, 21, 23, 41, 42, 43] 
[3, 5, 11, 16, 32, 38] 
[7, 11, 16, 35, 36, 44] 
[1, 8, 11, 31, 41, 42] 
[13, 14, 16, 38, 42, 45] 
[7, 11, 30, 40, 42, 43] 
[2, 13, 22, 32, 38, 45] 
[1, 3, 5, 14, 22, 45]

> 당첨 번호를 입력해 주세요. 1,2,3,4,5,6

> 보너스 번호를 입력해 주세요. 7

당첨 통계
--------------------
3개 일치 (5,000원) - 1개
4개 일치 (50,000원) - 0개
5개 일치 (1,500,000원) - 0개
5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
6개 일치 (2,000,000,000원) - 0개
총 수익률은 62.5%입니다.

> 다시 시작하시겠습니까? (y/n) 

```