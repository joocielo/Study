# javascript

### this
	this는 함수 내에서 함수 호출 맥락(context)를 의미한다. 맥락이라는 것은 상황에 따라서 달라진다는 의미인데 즉 함수를 어떻게 호출하느냐에 따라서 this가 가리키는 대상이 달라진다. 자바스크립트에서 this가 함수와 객체의 관계를 이어준다.

	함수안에서 사용하라 수 있는 약속된 변수이고, 그 함수를 어떻게 호출했냐에 따라서 this가 가르키는게 달라진다.

**함수 호출**

함수안에서 this는 전역객체(window)를 의미한다.
다른 방식으로 호출하면 this의 값이 바뀐다

- func()

**메소드의 호출**

객체 소속인 메소드의 this는 그 객체를 가르킨다.
- o.func()

**생성자의 호출**

생성자 안의 this -> 생성될 객체를 가르킴
*생성자가 실행되기 전까지는 객체는 변수에 할당되지 않는다.

**apply,call**

함수는 apply와 call이라는 메서드를 가지고 있다.

- function sum(x,y) {return x+y;} : 함수 리터럴
- var o = {} : 객체 리터럴
- var a = [1,2,3] : 배열 리터럴
  값을 만들 수 있게 도와주는 문법적인 체계를 리터럴이라고 한다.

apply(thisObj,argArray) : 함수를 호출하여 지정된 개체를 함수의 this 값으로 대체하고 지정된 배열을 함수의 인수로 대체한다.
	- thisObj : this로 사용될 개체
	- argArray : 인수로 사용될 배열


객체와 함수는 개별적인 것이다. 왜냐하면 함수도 객체이기 때문에. 근데 어떻게 호출했냐에 따라서 어떤 객체에 소속되는지가 결정된다.
