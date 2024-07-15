# NULL SAFETY 쓰는 법

## #1
```dart
class Person {
  String? name; // class 내의 변수를 초기화할 때 값을 선언해줘야 함. -> null이 들어올 수 있다면 ? 연산자를 써줘도 된다.
  
  String nameChange(String? name) { // 인자로 null을 가질 수도 있다.
    this.name = name;
    if(name == null){ // 그러므로 null check가 필요하다.
      return 'need a name';
    }else{
      return name.toUpperCase();
    }
  }
}

void main() {
  Person p = Person();
  if(p.name == null){ // 처음에 이 null check만 쓴다면, 클래스에서 null이 나오지 않을 것이기 때문에 삭제하라고 컴파일 에러가 뜬다. 그렇지만 위에서 null safety를 했기 때문에 더이상 에러가 뜨지 않는다. 
    print('need a name');
  }else{
    print(p.nameChange(p.name));
  }
}
```

## #2 변수값이 나중에 입력받아 할당되는 경우
```dart
class Person {
  late int age; // late 키워드 : 늦게 변수값을 초기화 하겠다
  
  int sum(int age, int num){
    this.age = age;
    int total = age + num;
    return
  }
}

void main() {
  Person p = Person();
}
```