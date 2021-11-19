# Fragment 추가, 교체

* MainActivity에 LoginFragment 추가
  
1. 
     ```Kotlin
    //setFrag method에서
    
    val ft = supportFragmentManager.beginTransaction() // 살짝 미들웨어 느낌

    .
    .
    .

   ft.replace(R.id.main_frame, LoginFragment()).commit() // MainActivity -> LoginFragment
   ```
<br></br>

* Fragment2(MainFragment)에 ChildFrag1(UserListFragment)추가

1. 이때. **childFragmentManager** 사용해야 됨!!!

2. Fragment2(MainFragment)에 layout id frag_container를 만들어야 됨.

3. ```Kotlin
    //setFrag method에서

    val ft = childFragmentManager.beginTransaction() // 살짝 미들웨어 느낌

    .
    .
    .

    ft.replace(R.id.frag_container, UserListFragment()).commit()
   ```

4. 여러개의 ChildFrag를 추가하려면 MainActivity.setFrag method 참고하기


<br></br>

## Fragment 교체

* Fragment1(LoginFragment)안에서 Fragment2(MainFragment)로 교체

> 1. Fragment1(LoginFragment) 안에서 MainActivity container를 Fragment2(MainFragment)로 교체
>
> 2. 이때, **parentFragmentManager** 사용해야 됨!!!!

<br></br>

# Press Back-Button

* 뒤로가기 기능

```Kotlin
    replace(R.id.container, fragmment2).
    addToBackStack(null). //중간에 이거 삽입하기.
    commit()
```

<br></br>

# 더 알아봐야 할 기능

1. popBackStackImmediate()
   
2. popBackStack()