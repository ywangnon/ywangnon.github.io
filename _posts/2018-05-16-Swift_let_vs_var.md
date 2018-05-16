let: 값이 안 변함
var: 변함

```
var str      = "dog"  // str value is "dog"
str          = "cat"  // str value is now "cat"

let strAnimal = "dog" // strAnimal value is "dog"
strAnimal     = "cat" // Error !
```

참조 타입의 값을 가질 때는 타입을 참조하는 객체를 바꿀 수는 없지만 객체의 값을 바꿀 수는 있다.

```
class CTest
{
    var str : String = ""
}

let letTest = CTest()
letTest.str = "test" // OK

letTest.str = "another test" // Still OK

//letTest = CTest() // Error

var varTest1 = CTest()
var varTest2 = CTest()
var varTest3 = CTest()

varTest1.str = "var 1"
varTest2.str = "var 2"
varTest3 = varTest1
varTest1.str = "var 3"

varTest3.str // "var 3"
```

클래스는 그 안의 값이 바뀌지만 구조체는 어떨까?

```

struct AAA
{
    var inner_value1    =   111

    mutating func
    mutatingMethod1()
    {
        inner_value1    =   222
    }
}


let aaa1    =   AAA()
aaa1.mutatingMethod1()      // compile error
aaa1.inner_value1 = 444     // compile error

var aaa2    =   AAA()
aaa2.mutatingMethod1()      // OK
aaa2.inner_value1 = 444     // OK
```

구조체는 그 값을 복사해서 가지고 있기 때문에 바뀌지가 구조체 안의 값이 바뀌지가 않는다.

내 생각에는 let은 값을 고정시킨다기 보다는 메모리로 잡힌 구역의 값을 고정시킨다고 느껴진다.
그래서 참조 타입은 주소만 가지고 있기 때문에 실질적으로 값을 가지고 있는 메모리 주소의 값은 바꿀 수 있는 것이다.
하지만 구조체는 값을 복사해서 가지고 있기 때문에 그 값을 바꿀 수 없는 것이라고 생각된다.

> [참조](http://code.i-harness.com/ko/q/16e3e2c)
