+++
title = "javaExample"
+++

```
public class Bus{
  private String name;
  private String color;
}
```

function sayHello(name,age){

console.log(“Hello!”,name,“you have”, age);

}

sayHello(“scw”, 20);

argument(인자)를 추가해서 외부에서 입력된 값을 콘솔에 출력하는 함수를 처음으로 짜보았다.

function sayHello(name,age){

console.log(“Hello!”+name+“you are”+age);

}

sayHello(“scw”, 20);

function sayHello(name,age){

console.log(Hello ${name} you are ${age} years old);

}

sayHello(“scw”, 20);

-> 백틱을 사용해서 표현하였다.

/\*function sayHello(name,age){

return Hello ${name} you are ${age} years old;

}

const greetNicolas = sayHello(“Nicolas”,14)

console.log(greetNicolas)

\*/

const calculator = {

plus : function(a, b){

return a+b;

}

}

//console.log(greetNicolas)

const plus = calculator.plus(5,5)

console.log(plus)

DOM(Document Object Model) 형태

const title = document.getElementById(“title”);

title.innerHTML = “Hi! From JS”;

title.style.color = “red”;

document.title = “I own you now”;

JavaScript 만 이용해서 html/css 를 수정하거나 추가할 수 있다.o/).

### Plese do something!

I really want to use this themes!
