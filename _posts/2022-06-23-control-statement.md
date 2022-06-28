---
layout: single
title: "0623 java control statement"
excerpt: "if/elseif/switch/for/while"
---



## 조건문

**1.  `if` / `else if`**

if, else if를 사용할 때는 진행순서를 생각한다.

큰 범위를 먼저 만나면 else if에 가기 전에 if문을 나가기 때문에 좁은 범위가 위로 올라가야 한다.

```java
public void test8() {
		Scanner sc = new Scanner(System.in);
		System.out.print("정수를 입력하세요. : ");
		int num = sc.nextInt();
		
		if(num > 1000) {
			System.out.println("10보다 큰 수 입니다.");
		} else if(num > 100) {
			System.out.println("100보다 큰 수 입니다.");
		} else if(num > 10) {
			System.out.println("10보다 큰 수 입니다.");
		}		//범위를 else if로 연결하는 경우 좁은 범위가 위로 가야 함
	}
```



**숫자 연산이 가능한 'char'의 성질을 이용하여 대소문자 변환 프로그램 만들기**

```java
public void exam4() { // A=65~90 a=97~122
		System.out.println("=======대/소문자 변환 프로그램========");
		Scanner sc = new Scanner(System.in);
		System.out.print("문자입력 : ");
		char alp = sc.next().charAt(0);
		
		if(65<=alp&&90>=alp) { //  a=65 1=49
			System.out.println("대문자를 입력하였습니다.");
			System.out.println("소문자로 변환 : "+(char)(alp+32));			
		} else if('a'<=alp&&'z'>=alp) { //97, 122를 소문자로 적어도 가능 (문자형만)
			System.out.println("소문자를 입력하였습니다.");
			System.out.println("대문자로 변환 : "+(char)(alp-32));
		} else {
			System.out.println("잘못입력하셨습니다. 영문자를 입력해주세요.");
		}
		// XOR연산을 이용해 "소문자로 변환 : "+(char)(alp^32)도 가능!
	}
```



**2. `switch`**

switch(조건문)에 해당하는 리터럴 값을 연산자로 계산기 프로그램 만들기

```java
public void exam3() {
		Scanner sc = new Scanner(System.in);
		System.out.println("========계산기 프로그램========");
		System.out.print("연산자를 입력하세요(+, -, *, /)");
		char ch = sc.next().charAt(0);
		System.out.print("첫 번째 정수를 입력하세요 : ");
		int num1 = sc.nextInt();
		System.out.print("두 번째 정수를 입력하세요 : ");
		int num2 = sc.nextInt();
		
		switch(ch) {
		case '+' :
			System.out.println(num1+"+"+num2+"="+(num1+num2));
			break;
		case '-' :
			System.out.println(num1+"-"+num2+"="+(num1-num2));
			break;
		case '*' :
			System.out.println(num1+"*"+num2+"="+(num1*num2));
			break;
		case '/' :
			System.out.println(num1+"/"+num2+"="+(num1/num2));
			break;
		default :
			System.out.println("다시 입력하세요.");
			break;
		}
	}
```

---------------------------





## 반복문

**1. `for`**

- 반복횟수가 정해져 있을 때 사용
- for ( 초기문 ; 조건문 ; 증감문 ) {  실행부 } ;
- 조건을 검사하여 true면, 실행부를 실행하고 증감문으로 이동한다
- 조건문이 false일 때까지 반복한다 

**num을 입력받아 num단 출력**

```java
public void prac1() {
		Scanner sc = new Scanner(System.in);
		System.out.print("몇 단을 출력하시겠습니까?");
		int num = sc.nextInt();
		for(int i=1; i<=9; i++) {
			System.out.printf("%d * %d = %d\n", num, i, num*i);
		}
	}
```



**2. `while`**

- 무한 반복하다가 특정 조건에 만족하여 나가는 경우

```java
public void exam5() {
		Scanner sc = new Scanner(System.in);
		System.out.print("숫자 입력 : ");
		int num = sc.nextInt();
		int sum = 0;
		int i = 0;
  
		while(i<=num) {
			sum += i;
			i += 2;
		}	System.out.println(sum);
	}
```





**`3. do while`**

- do { 실행부 } while ( 조건문 )
- 무조건 do의 실행부를 한 번은 실행하고, 조건문으로 넘어간다

```java
public void test2() {
	Scanner sc = new Scanner(System.in);
	System.out.print("정수를 입력하세요 : ");
     int num = sc.nextInt();
		/*
		while(num==10) {
		System.out.println("10을 입력하셨군요.");
		num++;
		} 	*/
		
	do { //조건을 검사하기 전에 무조건 실행문 출력
		System.out.println("10을입력하셨군요");
		num++;
	} while(num==10);
	}
```

