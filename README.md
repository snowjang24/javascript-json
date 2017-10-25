# javascript-json

## Array 분석
- 목적 : 배열의 선언을 문자열로 입력받아 문법이 유효한지 검사하고 입력한 데이터들의 type을 판별하여 각각의 개수를 출력한다.

- 요구사항 분석
  1. 대괄호의 열고 닫음이 올바른지 확인할 수 있어야 한다.
  2. double quote의 열고 닫음이 올바른지 확인할 수 있어야 한다.
  3. 공백을 처리할 수 있어야 한다.
  4. 문자열로 입력된 데이터들을 콤마(,)단위로 나눌 수 있어야 한다.
  5. 데이터의 type을 판별할 수 있어야 한다.

- flow chart
  1. 사용자로부터 데이터를 문자열로 입력 받는다.
  2. 입력받은 전체 문자열을 loop로 돌면서 double quote내에 존재하는 공백문자를 제외한 모든 공백을 제거한다.
     loop를 돌면서 double quote의 열고 닫음이 올바른지도 검증한다.
  3. 대괄호로 시작해서 대괄호로 끝나는가?
    - [yes]: 입력값에서 대괄호(시작과 끝)을 제거한다.
    - [no]: Error:'입력이 올바르지 않음' => GOTO(1)
  4. 콤마(,)단위로 입력값을 tokenize한 배열을 만든다.
  5. 배열을 순회하면서 아래 case들을 테스트한다.
    1. double quote로 시작해서 double quote로 끝나는가? //String인지 검사
      - [yes]: double quote를 제외한 값을 string 값으로 결과 배열에 저장.
      - [no]: Error:'double quote의 위치가 올바르지 않음.' => GOTO(1)
    2. 숫자인가?
      - [yes]: 해당 값을 Number type로 변환하여 결과 배열에 저장.
      - [no]: => GOTO(5.3)
    3. true || false?
      - [yes]: 해당 값을 boolean type으로 변환하여 결과 배열에 저장.
      - [no]: => GOTO(5.4)
  6. 결과 배열 출력.
