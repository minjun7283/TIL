# constructor

- constructor 오버로딩 생성자를 만들 수 있음



```kotlin

 import kotlin.contracts.contract
 fun main(){
    
    var a = b("hello")
}

class b(var c : String,var d: Int){
    constructor(name: Stirng) : this(name,9)

    
}

```

### 관련 내용
- [init 블럭](https://github.com/minjun7283/TIL/blob/master/Back-End/kotlin/%EC%B4%88%EA%B8%B0%ED%99%94%EB%B8%94%EB%9F%AD.md)