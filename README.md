# js_study

## 5-1

1. 함수의 기본형태 

    + 함수 선언식

        ```javascript
        function test() {
            return "hi"
        }
        ```
    + 함수 표현식

        ```javascript
        const test = function () {
            return "hi"
        }
        ```
    + 화살표 함수 
    
        ```javascript
        const test = () => {
            return "hi"
        }
        ```     
    + 즉시 실행 함수

        ```javascript
        (function () {
            return "hi"
        })();
        ```  
    함수에 인자를 받을때 ...문법을 이용하면 여러개의 인자를 배열로 받아올 수 있다.

    + ex1)
        ```javascript
        function test (...props) {
            console.log(props)
        }
        test(1,2)       // [1,2]
        test(1,2,3)     // [1,2,3]
        ```
    + ex2)
        ```javascript
        function test (a,b,...rest) {
            console.log(a,b,rest)
        }
        test(1,2,3,4,5,6)   // 1,2,[3,4,5,6]
        ```
    + ex3)
        ```javascript
        function test (...props) {
            console.log(props)
        }
        const arr = [1,2,3,4]
        test(arr)       // [[1,2,3,4]]
        test(...arr)    // [1,2,3,4]
        ```
    -------------------------------------  
2. 기본 매개변수

    이름 그대로 함수를 사용할떄 받는 요소에 기본값을 설정해 놓는 것.  
    만약 요소를 받지 못하면 기본값으로 함수를 계산한다.

    + ex)

        ```javascript
        function test (a=1) {
            console.log(a)
        }
        test()      // 1
        test(4)     // 4
        ```
-------------------------------------

## 5-2

1. Array method

    1. .forEach()  

        + 대상이되는 배열의 길이만큼 콜백함수를 호출한다.

            ```javascript
            const a = [1,2,3] // 길이 3
            a.forEach((prop, index)=> console.log(`a[${index}] = ${prop} 입니다.`))
            // a[0] = 1 입니다.
            // a[1] = 2 입니다.
            // a[2] = 3 입니다.
            ```
    
    2. .map()

        + 대상이되는 배열의 길이만큼 콜백함수 호출값을 새로운 배열에 담아 리턴한다.

            ```javascript
            const a = [1,2,3] // 길이 3
            const b = a.map((prop, index)=> `a[${index}] = ${prop} 입니다.`)
            console.log(b) // ["a[0] = 1 입니다.", "a[1] = 2 입니다.", "a[2] = 3 입니다."]
            ```

    3. .filter()

        + 대상이되는 배열에서 prop과 index를 받아 콜백함수의 조건을 만족했을때의 prop만 골라서 새로운 배열을 리턴한다.  
        이때 콜백함수에는 return값이 무조건 있어야한다.  
        ex) ()=>조건 or ()=>{return 조건}

            ```javascript
            const a = [1,2,3,4,5]
            const b = a.filter((prop)=> prop > 2) 
            console.log(b) // [3,4,5]
            ```
2. scope

    1. 충돌 해결법

        + 여러스크립트를 따오다보면 변수 중복선언 에러가 발생한다.  
        이때의 해결법은 다음과 같으며 이것을 섀도잉(내부변수가 외부변수를 가리다.) 라고 한다.

            ```
            1. 함수로 감싸거나, {} 안에 넣고 {} 안에서 호출하면 충돌이 발생하지 않는다. 

            2. 즉시 호출함수를 이용한다. 
            ```
        

-------------------------------------
-------------------------------------

## 8-1 예외 처리

1. 일반 적인 예외 처리

    ```javascript
    선택한 인자가 undefined 거나 null 값 등일 경우 if 문을 이용해 예외처리 할 수있다.
    let a = undefined
    
    if (a) {
        console.log("나는 실행되지 않습니다.!")
    }
    if (!a) {
        console.log("나는 실행됩니다.!")
    }

    ```
2. try~ catch~ finally

    ```javascript
    try {
        console.log("일단 실행해봐. 실행되면 ㅇㅋ")
    } catch (err) {
        console.log("와 안되네 그럼 안되는 err를 투척.")
    } finally {
        console.log("되든 안되든 그런거 모르겠고 난 무조건 실행!")
    }
    ```