# 10week

### **<질의응답>**

![2](https://github.com/hyeyuny/C_pg-3_group-notes-note-1/assets/144858340/ed49434d-1b44-40cf-adf7-6d4da973fcb3)


<aside>
💡 Swap 함수에 왜 &x, &y가 들어가는 거야? 그냥 x, y가 들어가면 안돼?

</aside>

**A.** 이 코드에서 두 개의 정수 값을 교환하는 역할을 해. 이때, 함수 내부에서 변수의 값을 바꾸려면 해당 변수의 주소를 알아야 해. 이 주소는 변수가 메모리의 어디에 위치하고 있는지를 알려주는 정보야. 이렇게 주소를 이용하면 함수 내에서 원래 변수의 값을 직접 바꿀 수 있어. 이걸 인자를 주소로 전달한다고 해. 그래서 함수에 변수 x, y의 주소를 넘기기 위해 &x, &y를 사용하는 거야.

반대로 &을 사용하지 않고 x, y를 넘긴다면 이는 인자를 값으로 전달한다고 해. 즉, 함수 내부에서는 원본 변수 x, y의 복사본을 만들어 사용하게 되므로 함수 내에서 복사본의 값을 바꾸더라도 x, y의 값이 변하지 않는 거지. 따라서 &을 사용해줘야 해.

<aside>
💡 예제 10-5에 인자 전달 방법 코드를 보면 n++가 있는데 왜 CountIncrement1 함수가 실행된 후에도 변수 a값이 변하지 않는 거야?

</aside>

**A**. CountIncrement1 함수가 실행된 후에 변수 a의 값이 변하지 않는 이유는 C 언어에서 함수의 매개변수로 값을 전달할 때, 매개변수로 전달되는 값은 복사되어 전달되기 때문이야.

CountIncrement1 함수의 정의 부분을 살펴보면

![1](https://github.com/hyeyuny/C_pg-3_group-notes-note-1/assets/144858340/3a6bde3c-00c8-44a8-a9ca-9dcaf758e8b5)

여기서 n은 매개변수로 받은 값의 복사본이며, 이 함수 내에서 n++은 해당 복사본을 증가시키는 거야. 이 증가된 값은 함수 내에서만 존재하고, 함수 외부의 실제 변수 a에는 영향을 주지 않아. 따라서, CountIncrement1 함수를 호출해도 a의 값은 변하지 않는 거야.

<aside>
💡 예제 10-8의 함수를 정의하는 부분에서 for문의 코드를

</aside>

```c
for(i = 0; i< Size ; i++)
	result += (*pA)++;
```

<aside>
💡 위와 같이 작성했을 때 왜 원하는 결과값 을 얻을 수 없는거야?

</aside>

**A.** 원래 코드에서 pA[i]는 배열의 i번째 요소를 참조하는 거야. 그래서 for문이 돌 때마다 다음 요소를 참조하게 되는 거지.

그런데 (*pA)++로 바꾸면, pA가 가리키는 곳, 즉 배열의 첫 번째 요소의 값만 계속 증가시키게 돼. 그래서 for문이 돌아도 다른 요소를 참조하지 못하고 계속 첫 번째 요소만 바라보게 되는 거야. 이렇게 되면 우리가 원하는 결과값을 얻을 수 없겠지.

<aside>
💡 그럼 이렇게 작성했을 때 SumArrat 함수는 배열의 모든 요소의 합을 계산하는 것이 아니라, 첫번째 요소의 값만 증가시키고 그 값을 더하는 동작을 Size번 반복한다는 말이지?

</aside>

**A.** 응. 잘 이해했어.