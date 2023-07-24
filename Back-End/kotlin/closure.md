# Closure란?

클로저(closure)란 지역함수로 함수안에서만 호출가능한 함수이다.

```kotlin
fun main(){
    print(function(3, 4))
    // 출력 : 7
    
    
    print(function2(1, 2))
    // 에러


}

private fun function(a: Int, b: Int): Int {
    fun function2(c: Int, d:Int): Int = c + d
    return a + b;
}
```

위 코드처럼 Closure 함수를 호출할떄 오류가 나는것을 알 수 있다.