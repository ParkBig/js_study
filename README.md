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