# 3 로직 : 조건 판단과 반복 수행

# 3.1 참과 거짓
- PHP프로그램의 모든 표현식은 참 또는 거짓이라는 진위값을 나타낸다.

# 3.2 조건 판단 (if())
- *if()* : 특정 조건이 참일때만 실행되는 구문
- *if() else* : 특정 조건이 참일때 if 구문 실행, 거짓 일때 else구문 실행
- *if() elseif()* : 여러 조건을 표현할때 사용

~~~~
//if, else if, else 함께 사용하기
if($logged_in) {
	print "환영합니다 정회원님";
} else if($new_messages) {
	print "방문자님, 새로운 메시지가 있습니다";
} else if($emergency){
	print "방문자님, 새로운 메시지는 없습니다만, 긴급 상황입니다";
} else{
	print "누구신지 모르겠으나, 새로운 메시지도 없고, 긴급상황도 아닙니다";
}
~~~~

# 3.3 복잡한 조건 설계
- 동일 연산자(==) : 두 값이 같으면 참 반환
- 부등 연산자(!=) : 두 값이 다르면 참 반환,동일 연산자의 반대
- 비교 연산자(<,>,<=,>=) : 두 값의 크기 비교
- 부정 연산자(!값) : 값이 거짓이면 참 반환
- 논리 연산자(&&) : 그리고 를 의미하여 두 표현식 모두 참인지 확인
- 논리 연산자(||) : 또는 을 의미하여 두 표현식 중 어느 하나라도 참인지 확인
- abs() : 입력한 인수의 절댓값 반환하는 함수
- strcasecmp(,) : 함수에 전달된 두 값이 같을때 0(거짓)을 반환, 따라서 같으면 참을 만들기 위해 부정 연산자와 같이 쓴다. 

~~~~
//부정연산자
if($icecream!=3){
	print '아이스크림은 3개가 아니다';
}
//부정연산자,strcasecmp()
if!strcasecmp($x,$y){
	print '$x는 $y와 같다';
}
~~~~
- 문자열 비교 : < 연산자와 > 연산자는 숫자와 문자열에 모두 사용할 수 있다. 사전순으로 먼저 나온 문자열이 더 작다고 판단한다.
- strcmp(,) : 문자열을 입력하면 사전순으로 첫번째 문자열이 두번째 문자열보다 크면 양수를, 작으면 음수를 반환한다.
- 우주선 연산자(<=>) : strcmp()와 비슷하지만 모든 자료형에 사용할 수 있다. 왼쪽이 크면 양수를, 작으면 음수, 같으면 0을 반환한다.
- 문자와 숫자를 비교할 때, 둘 다 문자여야지 사전순으로 비교한다. 하나라도 숫자면 숫자로 비교한다.
~~~~
//둘 다 사전순으로 비교
if("x54321">"x5678"){
	print '문자열 "x54321"은 문자열 "x5678"보다 크다';
}else{
	print '문자열 "x54321"은 문자열 "x5678"보다 작다';
}

$x=strcmp("x54321","x5678");
if($x>0){
	print '문자열 "x54321"은 문자열 "x5678"보다 크다';
}elseif($x<0)
	print '문자열 "x54321"은 문자열 "x5678"보다 작다';
}
//위에는 숫자 순서로, 아래는 문자(사전순)로 비교
if("6pack">"x55"){
	print '문자열 "6pack"은 문자열 "55"보다 크다';
}else{
	print '문자열 "6pack"은 문자열 "55"보다 작다';
}

$x=strcmp("6pack","55");
if($x>0){
	print '문자열 "6pack"은 문자열 "55"보다 크다';
}elseif($x<0)
	print '문자열 "6pack"은 문자열 "55"보다 작다';
}

//우주선 연산자 이용 <,>처럼 비교한다
//결과 : 문자열 "6pack"은 숫자 55 보다 작다->55가 6보다 크기 때문
$y='6pack'<=>55;
if($y>0){
	print '문자열 "6pack"은 숫자 55 보다 크다';
}elseif($x<0)
	print '문자열 "6pack"은 숫자 55 보다 작다';
}

~~~~

# 3.4 반복 실행(looping 루프구조)
- **while()** : 참이면 코드 실행, 결과가 참이면 다시 반복
~~~~
$i=1;
while($1<=10){
	print"<option>$i</option>\n";
	$i++;
}
~~~~
- **for(초기화 표현식, 조건표현식,순회 표현식)**
~~~~
for($i=1;$i<=10;i++){
	print"<option>$i</option>\n";
}
~~~~
