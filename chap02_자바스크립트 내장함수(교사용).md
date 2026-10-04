# JavaScript 내장 함수

---

# 1. String 객체 내장 함수

1.  문자열의 property : ① length

- 실습 : (17_string_object.html)

2.  내장 함수

    ② indexOf(찾고자 하는 문자열) : 찾고자 하는 문자열의 시작 인덱스 리턴(여러개라면 첫 문자열), 만약 없다면 -1을 리턴, indexOf(대상 문자열, 시작위치)로 작성 가능

    ③ lastIndexOf(찾고자 하는 문자열): 뒤에서부터 문자열을 찾아서 리턴

    ④ slice( ) : 문자열을 (시작 위치, 종료위치-1)만큼 잘라내기, 시작과 종료 위치에 음수를 사용 가능, 음수인 경우 끝부터 거꾸로 count

    ⑤ substring() : 문자열을 (시작위치, 종료위치-1)만큼 잘라내기, 시작과 종료 위치에 양수만 사용 가능 => 음수를 넣으면 0으로 처리

    ⑥ substr() : 시작위치와 잘라낼 길이를 파라미터로 갖는다. 글자 길이를 아는 경우 매우 효과적

         \* **substring vs substr vs slice**

    ⑦ replace(str1, str2): str1을 str2로 바꾼다. 단, 처음으로 나오는 단어에 한해서만 대소문자를 구분해서 바꾼다.

    ⑧ toUpperCase() : 모든 알파벳을 대문자로 변환

    ⑨ toLowerCase() : 모든 알파벳을 소문자로 변환

    ⑩ concat() : 여러 문자열(파라미터 갯수 제한 없음)을 합치기

    ⑪ trim() : 문자열의 앞, 뒤, 모든 공백을 제거(브라우져에 따라서 실행이 안 될 수도 있다)

    ⑫ padStart(길이, 문자열): 길이 만큼 앞을 문자열로 채운다. => 실무에서 많이 사용한다.

    ⑬ padEnd(맞출 길이, 채울 글자) : padEnd(문자열 전체길이, 뒤에 채울 문자열) => 거의 사용하지 않는다.

    ⑭ charAt() : 인덱스에 해당하는 문자 1개를 반환

    ⑮ charCodeAt() : 인덱스에 맞는 문자의 유니코드 값을 반환 => 거의 사용하지 않는다.

    \* split() : 파라미터로 전달받은 문자열로 변수에 할당된 문자를 나눠서 배열로 반환

    \* startWith() : 전달받은 문자열로 시작하는지 여부를 체크해서 boolean으로 리턴

    \* endsWith() : 전달달받은 문자열로 끝나는지 여부를 체크해서 boolean값으로 반환

---

# 2. Number 객체 내장 함수

- 실습 : (18_number_object.html)

  ① toString() : 문자열로 변환

  ② toExponential() : 지수 표기법으로 변환=> 사용 안 함

  ③ toFixed() : 소숫점 몇자리까지 보여줄지 결정하는 함수

  ④ toPrecision() : 정수와 소수점 모두를 합쳐서 몇자리까지 보여줄지 결정하는 함수
  //실무에서 거의 사용하지 않는다.

  ⑤ parseInt() : 문자를 정수로 반환 //전역함수이므로 문자열.parseInt( ) 가 아니라 parseInt(문자열)로 작성한다.

  ⑥ parseFloat() : 문자를 실수(부동소수점)로 변환

  ⑦ 부동소수점의 최대숫자, 최소 숫자 확인

  console.log(Number.MAX_SAFE_INTEGER); //9007199254740991

  console.log(Number.MIN_SAFE_INTEGER); //-9007199254740991

  ![alt text](image.png)

---

# 3. Array 객체 내장 함수 => 가장 중요한 객체 : 서버로부터 받아온 데이터 처리에 활용

- 실습 : (19_array_object.html)

  ① toString( ) : 쉼표를 기준으로 하나의 문자열로 변환

  ② join( ) : 파라미터로 전달된 문자를 이용해서 하나의 문자열로 변환하며 실무에서 많이 사용 => join의 활용 : 실무에서 많이 사용하며 많은 데이터양을 동적으로 불러올 경우 매우 효과적이다.
  - 태그 : table,thead,th,tbody,tr,td,button
  - 스타일 : border, margin-top, text-align, background-color
  - 속성 : id(자바스크립트에 document의 위치를 알려주기), class(스타일 대상 요소를 가리킴)
  - 이벤트 : 요소에 발생하는 동작 (button onclick = "함수")
  - 이벤트핸들러 : 이벤트에 해당하는 동작을 담은 함수

  ③ pop() : 배열의 마지막 요소 반환하고 배열에서 제거

  ④ push() : 배열의 마지막 요소 추가, join과 많이 사용

  ⑤ shift() : 배열의 첫 요소 반환하고 배열에서 제거 => 실무에서 많이 사용

        //서버 프로그램에서 많이 사용 => 요청을 배열에 쌓아두었다가

        //이벤트 큐에 순서대로 정리된 목록에서 1번 요청, 2번 요청...하나씩 꺼내서 작업을 처리

  ⑥ unshift() : 배열의 맨 앞에 요소를 추가하고 배열의 길이를 반환 => 실무에서 많이 사용

        //실무활용 => 음료를 데이터베이스에서 가져와서 일정한 기준으로 분류하여 활용한다고 가정해보자.
        이 때 등록하는 화면과 조회하는 화면이 다를 수 있다. 예를 들어 등록하는 화면에는 전체 option 이 필요하지 않지만,
        조회하는 화면은 전체 option이 필요하다.그러나 제공하는 함수는 맨 위 칸이 없는 상태로 제공될 가능성이 높을 때 활용하면 좋다.

  ![alt text](image-5.png)
  
  ⑦ splice(1, 2, 3) : 배열의 특정 위치에 새로운 요소를 추가

       //기존 요소를 삭제하면서 추가할 수 있다.

       //1. 새로운 요소를 추가할 인덱스 2. 요소를 추가하기 전에 삭제할 요소 수 3. 추가할 요소

  ⑧ concat() : 두 개 이상의 배열을 하나의 배열로 결합

  ⑨ slice( ) : 배열의 요소를 잘라내서 배열 형태로 반환(시작 인덱스, 마지막인덱스 -1)

  ⑩ sort() : 배열의 요소를 정렬해주는 함수로 매개변수가 함수이다. => 문자열 기준

  ![alt text](image-1.png)

  ⑪ filter( ) : 배열에서 특정 조건에 맞는 요소만 배열로 리턴

        //실무활용예제 : 사용자가 카테고리를 선택하고, 특정 조건의 상품만 보겠다고 체크했을 때 프론트엔드에서 데이터를 거르는 방법

  ⑫ map() : 배열의 모든 요소를 하나씩 돌면서 실행하고 새로운 배열을 생성하는 함수

        //실무활용예제 : 서버에서 받아온 json문자열을 화면에 보여줄 html 태그나 ui컴퍼넌트 배열로 변환할 때, for~ push() 보다 편의성이 좋다. 

  ⑬ reduce(p1, p2, p3, p4) : 배열요소의 누적 합을 구하는 함수, 또는 특정한 조건에 해당하는 값만 추출하는 함수
  //p1 : accumulator => 누적 값
  //p2 : currentValue => 현재 값
  //p3 : currentIndex => 현재 배열 인덱스, 생략 가능
  //p4 : arr => 전체 배열, 생략 가능

---

# 4. Date 객체 내장 함수

- 실습 : (20_date_object.html)

- 특징 : 현재의 년, 월, 일, 시, 분, 초, 밀리초 데이터를 얻어오는 객체

① 현재 날짜 객체 얻어오기 

      let now = new Date();
      console.log(now);

② 사용자가 날짜를 지정해서 객체를 얻어오기 

      let d = new Date(2025, 4, 29, 19, 34, 20, 0);
      console.log(d);

③ get() 함수의 활용 

      now.getFullYear(); //년도, ow.getMonth(); //월(0~), now.getDate(); //일, now.getDay(); //요일(일요일 0), 
      now.getHours(); //시간, now.getMinutes(); //분, now.getSeconds(); //초, const millisecind = now.getMilliseconds(); //밀리초

④ set() 함수의 활용  => get 함수에 대응하여 다 있다. 그러나 거의 사용하지 않는다.

      now.setFullYear(2021);
      console.log(now);

⑤ Date 객체의 활용 1. => 특정한 포맷으로 출력하고자 할 경우 

      toString()과 padStart(2, 0)를 잘 활용한다. 


⑥ 날짜별 조회 기능 구현(기준이 되는 시간 구하기)
      //1970-1-1
      let d2 = new Date(0); //밀리초를 입력해서 날짜를 구하는 것도 가능
      console.log(d2); //Thu Jan 01 1970 09:00:00 GMT+0900 (한국 표준시)

      //하루를 밀리초로 연산 : 24*60*60*1000
      console.log(new Date(24 * 60 * 60 * 1000)); //1970-1-2

      //오늘을 밀리초로 구하기 : getTime()함수는 특정 날짜와 시간을 밀리초로 계산 
      currentMilliseconds = now.getTime()
      console.log(currentMilliseconds);


⑦ 오늘을 기준으로 며칠 전, 후를 구하는 함수 만들기 

    const getIntervalDate = ((day) =>{
        let now = new Date();
        let dayMilliseconds = 24 * 60 * 60 * 1000; //하루
        let intervalDate = now.getTime() + day * dayMilliseconds;
        return new Date(intervalDate);
    }); 

⑧ Date 객체의 활용 2. => 오늘을 기준으로 day일전과 마지막 날짜를 오늘로 화면에 뿌리기 

    const getIntervalDateformat = ((day, format) => {
          


     });
    before7days = getIntervalDateformat(-7, "YYYY-MM-DD");
    document.getElementById("startDate").value = before7days;
---

# 5. Set 객체 내장 함수

- 실습 : (21_set_object.html)

- 특징
  - ECMA 6버전에서 추가된 객체
  - 배열과 매우 유사하나, 유일한 요소만 갖는다.
  - 따라서 기존의 긴 소스들을 간단하게 줄일 수 있다.
  - 필요한 데이터의 특성(고유한 데이터)에 따라 Set 을 사용하면 많은 수고를 줄일 수 있다.
  - 파이썬처럼 add, has, delete, clear 등의 함수를 내장하고 있다.

---

# 6. Map 객체 내장 함수

- 실습 : (22_map_object.html)

- 특징
  - key 와 value 로 이루어진 객체, 마치 Object 와 유사
  - key에 문자가 아닌 값이 올 수 있으므로, 키가 문자열이 아닌 object를 만들고자 할 경우 대체제로 활용이 가능
  - 파이선의 딕셔너리와 유사
  - Object 와 Map의 차이
![alt text](image-2.png)
  - 주요 메서드 : key, values, set, get, has, delete, clear
  - map은 iterable객체이므로 forEach()를 사용하면 매우 효과적이다. map이름.forEach(함수)

    예시)  personMap.forEach((person) => { 

              console.log(person);

          });



---

# 7. Math 객체 내장 함수

- 실습 : (23_math_object.html)

  ① round() : 반올림처리 => 실무에서 사용 많음

  ② ceil() : 올림처리 => 실무에서 사용 많음 => 페이징처리

  ③ floor() : 내림

  ④ trunc( ) : 소수점 이하는 무조건 버림

      **floor() vs trunc()** ?

  ⑤ sign() : 양수이면 1, 음수이면 -1, 0 => 거의 사용 안 함

  ⑥ pow() : 제곱값

  ⑦ sqrt() : 제곱근값

  ⑧ abs() : 절대값

  ⑨ min() : 최소값

  ⑩ max() : 최대값

  ⑪ random() : 랜덤값 => 0보다 크거나 같고 1보다 작은 값을 무작위로 발생 => 가장 실무에서 많이 사용

  //활용1. 0~9

  //활용2. 1~10

  //활용3. 1~100

  //활용4. 시작값과 종료값을 주면 사이값을 random하게 나오게 하는 함수를 작성하여 활용해보자


- 활용 실습예제 : 컴퓨터와 가위, 바위, 보를 하는 게임을 작성해보자. (24_rsp_player.html)
![alt text](image-3.png)

---

# 8. JSON 객체 내장 함수

-실습 : (25_json.html)

1. JSON(Javascript Object Notation)

- 데이터를 저장하거나 전송 시 많이 사용하는 데이터 교환 형식(데이터 포맷)
- 클라이언트와 서버간의 데이터 전송 시 가장 많이 사용하는 포맷
- Object 표기법과 동일(cf : 키에 “ ”가 있고, 선언자가 없다)
- 프로그래밍 언어와 관계없이 사용할 수 있는 데이터 교환 형식
- 대부분의 프로그래밍 언어에서 json을 처리할 수 있는 라이브러리를 제공

2. JSON.stringify( ) : 클라이언트에서 서버로 전송시 자바스크립트 데이터를 문자열로 변환
3. JSON.parse( ) : 서버에서 클라이언트로 전송시 문자열을 자바스크립트 객체로 변환

---

# 9. windows 객체 내장 함수

- 실습 : (26_window_pbject.html)

1. alert() : 경고 창, 모양 관계로 거의 사용하지 않는다.
2. prompt() : 문자를 입력받는 창 => 모양 관계로 거의 사용하지 않는다.
3. confirm( ) : yes or no 를 진행하는 창 => 모양 관계로 거의 사용하지 않는다.
4. open() : 새 창 열기 => 모양 관계로 거의 사용하지 않는다.
5. setTimeout() : 지정한 초가 지난 다음 1회 실행
6. setInterval() : 시간간격으로 반복 실행 => 웹소켓 이전 많이 사용

   - 웹소켓 이전에 주기마다 나타나는 주식 등의 데이터에 reponse하는 용도로 많이 사용했으나 너무 많은 트래픽으로 인해 서버 다운의 문제점 발생

   - 노드에서는 데이터가 변할 때만 자료를 주는 웹소켓 방식으로 변화....

7. clearInterval(), clearTimeout() : setInterval을 중지시키는 역할
