# kotlin-lotto

# 1단계 - 문자열 덧셈 계산기
## 기능 요구사항
- 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환
  (예: “” => 0, "1,2" => 3, "1,2,3" => 6, “1,2:3” => 6)
  - [x] 문자열 덧셈 계산기 객체를 가진다. 
    - [x] 유효한 문자열을 전달할 경우 합계를 반환한다.
    - [x] 공백을 전달하면 0을 반환한다.
    - [x] 유효하지 않은 값을 전달하면 예외를 던진다.
- 문자열 계산기에 숫자 이외의 값 또는 음수를 전달하는 경우 예외를 던진다.
  - [x] 숫자 값 객체를 가진다. 
    - [x] 숫자 혹은 숫자로 변경가능한 문자를 전달하면 정상적으로 객체가 생성된다.
    - [x] 숫자가 아니거나 숫자로 변환될 수 없는 값을 전달하면 예외를 던진다.
    - [x] 음수를 전달할 경우 예외를 던진다.
  - [x] 문자열 분리자를 가진다. 
    - [x] 기본 구분자 `,`, `:`으로 문자열을 분리할 수 있다.
- 앞의 기본 구분자(쉼표, 콜론) 외에 커스텀 구분자를 지정할 수 있다.    
  커스텀 구분자는 문자열 앞부분의 “//”와 “\n” 사이에 위치하는 문자를 커스텀 구분자로 사용한다.    
  예를 들어 “//;\n1;2;3”과 같이 값을 입력할 경우 커스텀 구분자는 세미콜론(;)이며, 결과 값은 6이 반환되어야 한다.
  - [x] 커스텀 문자열 분리자를 가진다.
    - [x] `//`와 `\n` 사이의 구분자를 찾을 수 있다. 
    - [x] `//`와 `\n` 사이에 구분자가 없을 경우 예외를 던진다.
    - [x] 커스텀 구분자로 문자열을 분리해서 반환할 수 있다.
    - [x] 커스텀 구문자 블럭외에 값이 존재하지 않을 경우 빈 리스트를 반환한다.
    - [x] 숫자는 커스텀 구분자가 될 수 없다.


## 프로그래밍 요구 사항
- indent(인덴트, 들여쓰기) depth를 2를 넘지 않도록 구현한다. 1까지만 허용한다.
  - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
  - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메서드)를 분리하면 된다.
- 함수(또는 메서드)의 길이가 10라인을 넘어가지 않도록 구현한다.
  - 함수(또는 메서드)가 한 가지 일만 잘 하도록 구현한다.

---

# 2단계 - 로또(자동)
## 기능 요구사항
- 로또 구입 금액을 입력하면 구입 금액에 해당하는 로또를 발급해야 한다.
  - [x] 돈 객체를 가진다. 
    - [x] 0원 이상의 자연수를 전달하면 돈 객체가 생성된다.
    - [x] 0원 이상의 자연수로 변환 가능한 문자열을 전달하면 돈 객체가 생성된다.
    - [x] 유효하지 않은 인자를 전달하면 예외를 던진다. 
      - [x] 공백을 전달하면 예외를 던진다. 
      - [x] 음수를 전달하면 예외를 던진다. 
      - [x] 숫자로 변환이 될 수 없는 문자를 전달하면 예외를 던진다.
  - [x] 로또 발급 서비스를 가진다. 
    - [ ] 로또 한 장 금액 이상의 금액을 전달하면 적절한 자동 로또 목록을 반환한다. 
    - [ ] 로또 한 장 금액 이하의 금액을 전달하면 빈 목록을 전달한다.
- 로또 1장의 가격은 1000원이다.
  - [x] 로또 객체를 가진다.
    - [ ] 로또는 중복되지 않는 6개의 숫자를 전달받으면 정상적으로 생성된다.
    - [ ] 로또는 6개의 숫자가 아니면 예외를 던진다.
    - [ ] 전달된 로또 번호는 오름차순으로 정렬 된다.
  - [x] 로또 번호 객체를 가진다. 
    - [ ] 로또 번호는 1 ~ 45 이내의 숫자여야 한다.
    - [ ] 로또 번호가 1 ~ 45 이외의 숫자일 경우 예외를 던진다. 
    - [ ] 로또 번호는 캐싱되어 있으며 같은 번호 객체는 동등성과 동일성 모두 일치한다.
  - [x] 로또 번호 목록 생성기를 가진다. 
    - [ ] 중복되지 않는 6개의 로또 번호 목록을 반환한다.
  - [x] 로또 일급 컬렉션을 가진다. 
    - [ ] 당첨 번호 객체를 전달하면 당첨 통계 정보를 반환 한다.
- 당첨 번호로 하나 이상의 당첨 로또를 찾을 수 있다. 
  - [x] 당첨 번호 객체를 가진다. 
    - [ ] 당첨 번호는 중복되지 않는 6개의 로또 번호를 가진다. 
    - [ ] 6개가 아닌 로또 번호를 전달하면 예외를 던진다.
    - [ ] 로또를 전달하면 당첨 등수를 반환 한다.
  - [x] 로또 랭킹 타입을 가진다. 
    - [ ] 로또와 당첨번호의 동일한 숫자 갯수에 따라 등수를 반환한다. 
    - [ ] 등수별 우승 상금정보를 가진다. 
  - [x] 수익율 계산기 객체를 가진다. 
    - [ ] 구입금액과 당첨금을 가지고 수익율을 계산해 반환한다.
    
  


## 프로그래밍 요구 사항
- 모든 기능을 TDD로 구현해 단위 테스트가 존재해야 한다. 단, UI(System.out, System.in) 로직은 제외
  - 핵심 로직을 구현하는 코드와 UI를 담당하는 로직을 구분한다.
  - UI 로직을 InputView, ResultView와 같은 클래스를 추가해 분리한다.
- indent(인덴트, 들여쓰기) depth를 2를 넘지 않도록 구현한다. 1까지만 허용한다.
  - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
  - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메서드)를 분리하면 된다.
- 함수(또는 메서드)의 길이가 15라인을 넘어가지 않도록 구현한다.
  - 함수(또는 메서드)가 한 가지 일만 잘 하도록 구현한다.
- 기능을 구현하기 전에 README.md 파일에 구현할 기능 목록을 정리해 추가한다.
- git의 commit 단위는 앞 단계에서 README.md 파일에 정리한 기능 목록 단위로 추가한다.
