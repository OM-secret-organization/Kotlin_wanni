# 아이템2. 변수의 스코프를 최소화하라

프로퍼티 보다는 지역변수를 사용하는 것이 좋다.

최대한 좁은 스코프를 갖게 변수를 사용한다. 반복문 내부에서만 변수가 사용된다면 변수를 반복문 내부에 작성하는 것이 좋다.

```kotlin
// BAD
var user: User
for (i in users.indices) {
  user = users[i]
  print("User at $i is $user")
}

// Better
for (i in users.indices) {
	val user = users[i]
  print("User at $i is $user")
}

// More than Better
for ((i, user) in users.withIndex()) {
  print("User at $i is $user")
}
```