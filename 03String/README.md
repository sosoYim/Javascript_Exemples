# 정규식 표현

> 일정한 패턴을 가진 문자열의 집합을 표현하기 위해 사용하는 형식 언어(formal language)
> /pattern/i

[regexr.com](https://regexr.com/)

## 예제 링크

1.  [유효한 팰린드롬]('./01\_유효한 팰린드롬.js')

## 주요 메서드

- `RegExp.prototype.exec` => 첫 번째 매칭 결과 반환 || null
- `RegExp.prototype.test` => boolean값 반환
- `RegExp.prototype.match` => 매칭 결과 배열로 반환

```jsx
const target = 'Jim, did you closed the door ? Hey Jim !';
const regExp = /Jim/;
const regExpG = /Jim/g;

regExp.exec(target);
/*[
  'Jim',
  index: 0,
  input: 'Jim, did you closed the door ? Hey Jim !',
  groups: undefined
]*/
regExp.test(target); // true
target.matches(regExpG); // [ 'Jim', 'Jim' ]
```

## 주요 표현식

### flag

- i : Ignore case
- g : Global
- m : Multi line

### 패턴

> 조건에 따른 문자열을 반환한다.

- /.../ => 임의의 문자열 (. 마침표는 자리수)
- {1,3} => 반복문자{최소, 최대}
- {1,} => 반복문자{최소,}
- \+ => 최소 1번 이상 반복 문자 A+
- /colou?r/ => ? u가 0번 혹은 한 번 이상 반복
- /A+|B+/ => A나 B가 한 번 이상 반복
- [AB] => 위와 같음.
- [^f] => not
- [com$] => 마지막 문자열
- /^\d$/ => 숫자열로만 이루어진 문자열
- \d : 숫자
- \w : 숫자, \_
- \s : 공백
- \W : 알파벳, 숫자, 언더스코어가 아닌 문자

  // \w : 숫자, \_
  // + : 하나 이상
  // \. : 아무 문자나
  // {2,} : 두 개 이상
  // | : or
  // ^ : start
  // $ : end
  // [^] : not
  // /^$/ : 빈 문자열