### 포인터

{2020년 8월 21일 금요일}

1. 포인터 형식 : **자료형 포인터명;**

ㄱ.  포인터변수는 변수의 주소값을 저장

ㄴ. 포인터 변수가 가리키는 변수의 값에 접근할 떄는 *를 붙인다

ㄷ. 배열의 엔덱스에 접근할 때 : **sarr[i] == *(sptr+i)**

	2. 배열명은 배열의 주소이며, 배열의 첫 번째 값의 주소와 같다

ㄱ. 포인터가 가리키는 주소 : 배열의 첫 번째 값의 주소

ㄴ. scanf로 입력받을 때나 포인터로 가리킬 때 배열명 앞에 &를 붙일 필요가 없다

	3. 메모리 주소 출력 형식지정자 : %d(10진수), &p(16진수)



```c
#include <stdio.h>

int main(){
	int i, a[10]={0, 1, 2, 3, 4, 5, 6, 7, 8, 9}, *ap=a;
	for(i=0; i<10; i++){
		a[i]+=1;
		printf("%d ", *ap+i);
	}
	printf("\n");
	printf("%d\t, %p\n", a[0], &a);
	printf("%d\t, %p\t %p\n", *ap, ap, &ap);
	ap=&i;
	*ap=30;
	printf("%d\t, %p\n", i, &i);
	printf("%d\t, %p\t %p\n", *ap, ap, &ap);
	
	return 0;
}
```



```c
#include <stdio.h>

int main(){
	int a=12, *ptr=&a;
	char sarr[12]="It'sStrring";
	char *sptr=sarr;
	printf("%d %d\n", a, *ptr);
	int b= *ptr+10;
	printf("%s\n", sptr);
	*ptr=35;
	printf("%d %d\n", b, a);
	return 0;
}
```

[길이가 10인 int형 배열 arr을 1~10으로 초기화 한 다음, 1번 2번 문제를 풀어라]

<1> 배열의 첫 번째 요소를 가르키는 포인터 변수(p)를 선언한다, p를 이용하여 모든 배열요소의 값을 2씩 증가시키고 출력하라.

```c
#include <stdio.h>

int main(){
	int arr[10]={1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
	int *p=arr;
	for(int i=0; i<10; i++){
		*(p+i)+=2;
		printf("%d ", *(p+i));
	}
	return 0;
}
```

<2>

```c
#include <stdio.h>

int main(){
	int arr[10]={1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
	int *p=arr;
	int *q=&arr[9];
	int sum;
	for(int i=0; i<5; i++){
		sum = *(p+i);
		*(p+i)=*(q-i);
		*(q-i) = sum;
	}
	for(int i=0; i<10; i++){
		printf("%d ", *(p+i));
	}
	return 0;
}
```

