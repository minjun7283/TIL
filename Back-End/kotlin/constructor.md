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