# Data 선언 및 사용

### 선언
* ``<script>``태그 내에 data() 생성하여 작성
  
```js
export default {
    data() {
        return {
            title: "안녕 뷰야",
            title2: "반가워",
            input1: "방가방가",
        };
    }
}
```

### 사용

* ``<template>`` 태그 영역 내에서

```js
<h1> 만나서 반가워 {{title}} </h1> //만나서 반가워 안녕 뷰야
```

* ``<input>`` 태그 text속성과 바인딩

    * 기존 js의 경우 value 속성에 접근하여 바인딩했지만 vue.js의 경우 ``v-model`` 속성을 이용하여 바인딩 함.

        ```html
        <input type = "text" v-model = "input1">
                                    <!--방가방가-->
        ```
    
### Tip

* watch 기능 : 변수의 이름을 함수의 이름으로 하여 변수의 값이 변경될때마다 함수가 호출 됨.
  
```js
export default {
    data() {
        return {
            title: "안녕 뷰야",
            title2: "반가워",
            input1: "방가방가",
        };
    },
    watch: {
        input1(){
            console.log(this.input1); //input1 은 input 태그 text 속성에 바인딩 되어 있다고 가정
        },
    },
}
```

<br>

# Method 선언 및 사용

### 선언
* ``<script>``태그 내에 methods: 생성하여 모든 메소드 여기에 선언
  
```js
export default {
    data() {
        return {
            title: "안녕 뷰야",
            title2: "반가워",
            input1: "방가방가",
        };
    },
    methods: {
        
        getData(){
            alert(this.input1); //메소드 내에서 data 에 접근하기 위해서는 this 객체 삽입해야됨.
        },
        setData(){
            this.input = "12345" // 변수 input 의 값이 12345 로 변경 됨.
        }
    }
}
```

### 사용

* ``<template>`` 태그 영역 내에서

* ``<input>`` 태그 클릭 이벤트 시

    * 기존 js 의 경우 onclick 속성을 통해 메소드를 호출 함

    * Vue.js 에서는 **@click** 을 통해서 메소드 호출

        ```html
        <button type = "button" @click="getData">Get</button>
        ```