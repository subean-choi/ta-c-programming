# C언어 프로그래밍(1) TA

✉️ [redacted email]
📱 [redacted phone]
✉️ [redacted email]
## ☘️ TA 운영 계획


### 📖 TA 세션
💬 **c언어 프로그래밍(1) ta 오픈 채팅방**
💻 **c언어 프로그래밍(1) ta Discord**
---
### 📘 Embedded System Online judge
[http://eseoj.inu.ac.kr/JudgeOnline/](http://eseoj.inu.ac.kr/JudgeOnline/)




### 1️⃣ 복습
⏰ 대략 1시간 이상
📄 월요일 배운 내용들 복습


### 2️⃣ 실습
⏰ 복습 후 나머지 시간
📄 복습 내용 실습
→ 온라인 저지 사용


### 3️⃣ 질의 응답
⏰ 이외 모든 시간


### 📅 Calendar
> Notion database:  C언어 프로그래밍 일정
---
# 📚 주차 별 정리 모음
- 1-3주차 정리 (3/4\~3/22)
- 4주차 정리 (3/25\~)
- 5주차 (4/1\~)
- 중간고사 코드
- 9주차 실습 코드
- 10주차 강의 내용
- 11주차 강의 내용
# 💬 Question 모음
- 문자형 char를 1byte 이상 입력하고 싶을때
- 자료형 중 longlong이 사용되는 경우
- scanf와 scanf_s의 차이
- 자료형 char에 하나의 철자를 쓴다면 왜 작은 따옴표를 사용해야하는지
- 함수 return값에 따른 반환형 
- scanf 위치에 따른 출력값의 변화
-  반복문에서 count되는 값에 따른 출력값 변화

---

# 1-3주차 정리 (3/4~3/22)

### 🔧 Visual Studio 설치 방법
[attached course file]
### 📄 Embedded System Online judge 사용 방법
[attached course file]
### ✏️ 1, 2, 3주차 강의 pdf
[attached course file]

---

# 4주차 정리 (3/25~)

### ✏️ 4,5주차 강의 pdf
[attached course file]
[attached course file]

---

# 5주차 (4/1~)

### ✏️ 5주차 강의 pdf
[attached course file]

---

# 중간고사 코드

### 1번
양의 정수들이 입력될 때, 그 중 짝수와 홀수의 개수를 각각 카운트하고, 숫자 0이 입력되면, 짝수와 홀수 개수를 공백 1개 문자로 구분하여 출력하고 종료하시오. 짝수 개수를 먼저 출력하고, 공백 1칸 후에 홀수 개수를 출력한다.
```c
int main()
{
int input;
int o_cnt = 0, e_cnt = 0; // odd 홀수, even 짝수

while (1)
{
scanf("%d", &input);
if (input == 0)break;
if (input % 2 == 0) e_cnt++;
else if (input % 2 != 0)o_cnt++;
}

printf("%d %d", e_cnt, o_cnt);
return 0;
}
```
### 2번
양의 정수 3개가 입력될 때, 가장 큰 수와 가장 작은 수를 출력하되, 공백 1개로 구분하여 출력하시오. (배열을 사용하여 구현할 경우, 학점 F 처리됩니다.)
```c
int main()
{
int num1, num2, num3;
scanf("%d %d %d", &num1, &num2, &num3);

int max = num1;
int min = num1;

if (max < num2)max = num2;
if (max < num3)max = num3;

if (min > num2)min = num2;
if (min > num3)min = num3;

printf("%d %d", max, min);
return 0;
}
```
### 3번
양의 정수 4개가 입력될 때, 가장 큰 수와 가장 작은 수를 출력하되, 공백 1개로 구분하여 출력하시오. (배열을 사용하여 구현할 경우, 학점 F 처리됩니다.)
```c
int main()
{
int num1, num2, num3, num4;
scanf("%d %d %d %d", &num1, &num2, &num3, &num4);

int min = num1;
int max = num1;

if (max < num2)max = num2;
if (max < num3)max = num3;
if (max < num4)max = num4;

if (min > num2)min = num2;
if (min > num3)min = num3;
if (min > num4)min = num4;

printf("%d %d", max, min);
return 0;
}

```
### 4번
양의 정수 A와 B (A \< B)가 입력될 때, A와 B 사이 (A, B 제외하고)의 모든 소수들의 합을 출력하시오.
```c
int main()
{
int num1, num2;
scanf("%d %d", &num1, &num2);
int sum = 0;

for (int i = num1 + 1; i < num2; i++) {
int check = 0;
for (int j = 2; j < i; j++) {
if (i % j == 0) {
check++;
}
}
if (check == 0) {
sum = sum + i;
}
}

printf("%d", sum);
return 0;
}
```
### 5번
양의 정수가 입력되면, 순서를 뒤집어서 출력하시오.
```c

int main()
{
int num;
scanf("%d",&num);

while (num > 0)
{
printf("%d", num % 10);
num = num / 10;
}
return 0;
}
```
### 6번
양의 정수 n이 입력되면, n! (n factorial)을 계산하고, 그 결과보다 작은 소수의 개수를 출력하시오.
```c
int main()
{
int num;
scanf("%d", &num);
int fac = 1;
int cnt = 0;

//fac구하기
for (int i = 1; i <= num; i++) {
fac = fac * i;
}

//소수 구하기
for (int i = 2; i < fac; i++) {
int check = 0;
for (int j = 2; j < i; j++) {
if (i % j == 0)check++;
}
if (check == 0) {
cnt++;
}
}

printf("%d", cnt);
return 0;
}
```
### 7번
피보나츠 수열은 0, 1, 1, 2, 3, ... 과 같이 바로 직전의 숫자 2개의 합을 값으로 가지는 숫자들의 열이다. 입력정수 N보다 작은 값을 가지는 피보나츠 수열에 속한 숫자의 개수를 출력하시오. 예를 들어, N=4이면, 5개 (0, 1, 1, 2, 3) 이다.
```c
int main()
{
int num;
scanf("%d", &num);
int cnt = 0;
int fibo;

int ppre = 0;
int pre = 1;

if (num != 0) {
cnt++;
}
while (pre < num) {
fibo = pre + ppre;
ppre = pre;
pre = fibo;

cnt++;
}
printf("%d", cnt);
return 0;
}
```
### 8번
양의 정수 N이 입력되면, 1부터 N까지의 합, 1부터 N-1, ..., 1부터 3, 1부터 2까지 합을 공백 1개로 구분하여 출력하시오. 예를 들어, N=3이면 6 3 이 출력된다. 6 = (1 + 2 + 3) 3 = (1 + 2)
```c
int main()
{
int num;
scanf("%d", &num);

for (int i = num; i >1; i--) {
int sum = 0;
for (int j = 1; j <= i; j++) {
sum = sum + j;
}
printf("%d ", sum);
}
return 0;
}
```
### 9번
양의 정수 N을 입력받아, 이 숫자와 가장 가까운 소수를 출력하시오. N은 소수일 수도 있지만, 자기 자신은 제외한다. 가장 가까운 소수가 2개면, 그 중 작은 수를 선택한다. 예를 들어, N=10이면, 가장 가까운 소수는 11이다. N=8이면, 가장 가까운 소수는 7이다. N=12이면, 가장 가까운 소수는 11이다.
```c
int main()
{
int num;
scanf("%d", &num);

int n1 = 0;
int n2=999999;
for (int i = 2; i < num; i++) {
int check = 0;
for (int j = 2; j < i; j++) {
if (i % j == 0)check++;
}
if (check == 0) {
if (n1 < i)n1 = i;
}
}

for (int i = num+1; i < num + (num - n1); i++) {
int check = 0;
for (int j = 2; j < i; j++) {
if (i % j == 0)check++;
}
if (check == 0) {
if (n2 > i)n2 = i;
}
}
if (n2 != 999999) {
printf("%d", n2);
}
else {
printf("%d", n1);
}
return 0;
}
```
### 10번
양의 정수 N과 A를 입력받는다. A는 한자리 양의 정수이다. 1 \~ N까지의 숫자들 (1과 N포함) 중에서, 어느 자리 수이든 상관없이, A가 나타나는 횟수를 출력하시오. 예를 들어, N=11, A=1 이면, 답은 4가 된다. 왜냐면, 1은 1, 10, 11(1이 2개)에서 나타나기 때문이다.
```c
//10번
int main()
{
int N, A;
scanf("%d %d", &N, &A);
int cnt = 0;

for (int i = 1; i <= N; i++) {
for (int j = i; j > 0; j = j / 10) {
if (j % 10 == A)cnt++;
}
}
printf("%d", cnt);
return 0;
}
```

---

# 9주차 실습 코드

### 1번
```javascript
int main()
{
int num;
scanf("%d",&num);

int max = 0;
int cnt_s = 0;

for (int i = 2; i <= num; i++) {
int cnt = 0;
for (int j = 2; j < i; j++) {
if (i % j == 0)cnt++;
}
if (cnt == 0) {
if (max < i) {
max = i;
}
cnt_s++;
}
}
printf("%d", cnt_s + max);
}
```
### 2번
```javascript
int main()
{
int num, num1;
scanf("%d %d", &num, &num1);
int cnt = 0;

for (int i = 0; i <= num1; i++) {
int check = 0;
for (int j = i; j > 0; j = j/10) {
if ((j%10) == num) {
check++;
}
}
if (check != 0) {
//printf("%d ", i);
cnt++;
}
}

printf("%d", cnt);
}
```
### 3번
```javascript
int main() {
int num;
int cnt = 0;
scanf("%d", &num);

while (num > 0) {
if (cnt % 2 != 0) {
printf("%d", num % 10);
}
num /= 10;
cnt++;
}
printf("\n");

return 0;
}
```
### 4번
```javascript
int main()
{
int num;
int max = 0, min = 9999;

while (1) {
scanf("%d", &num);
if (num == 0)break;

if (max < num)max = num;
if (min > num)min = num;
}

int a = max - min;
int b;

int pre = 1, prepre = 0;
if (a == 0)printf("%d", 0);
else if (a == 1)printf("%d", 1);
else {
for (int i = 2; i <= a; i++) {
b = pre + prepre;
prepre = pre;
pre = b;
}
printf("%d\n", a);
printf("%d", b);
}
}
```
### 5번
```javascript
int fac(int a)
{
int ans = 1;
for (int i = 1; i <= a; i++) {
ans = ans * i;
}
return ans;
}

int main()
{
char c;
int cA = 0;
int ca = 0;

while (1)
{
scanf("%c", &c);
if (c == '@')break;
if (c >= 'a' && c <= 'z')ca++;
else if (c >= 'A' && c <= 'Z')cA++;
}

//printf("%d %d %d %d", ca,cA,fac(ca),fac(cA));
printf("%d", fac(cA) + fac(ca));
}
```
### 6번
```javascript
int a;
int b;

int add()
{
return a + b;
}

int main()
{
scanf("%d %d", &a,&b);
printf("%d", add());

return 0;
}

```
### 7번
```javascript
int whoMax(int a)
{
static int max = 0;

if(max < a){
max = a;
}

return max;
}

int main()
{
int num;
int a;
while (1) {
scanf("%d", &num);
if (num == 999)break;
else a=whoMax(num);
}
printf("%d", a);
}
```
### 8번
```javascript
//7번
int mul(int a)
{
static int sum = 1;
if (a == 0) {
return sum;
}
else {
sum = sum * a;
return 0;
}
}

int main()
{
int num;
while (1) {
scanf("%d", &num);
if (num == 0)break;
else mul(num);
}
printf("%d", mul(num));
}
```

---

# 10주차 강의 내용

### 10주차 배열 강의 pdf
[attached course file]
### 10주차 TA 강의 코드
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

/*
int main()
{
char ans;
int ans1;
int seat[10] = { 0 };

while (1) {
printf("좌석을 예약하시겠습니까? (y또는n):\n");
scanf("%c", &ans);

if (ans == 'n')break;
printf("----------------------\n");
printf("1 2 3 4 5 6 7 8 9 10\n");
printf("----------------------\n");

for (int i = 0; i < 10; i++) {
printf(" %d", seat[i]);
}
printf("\n");

printf("몇번째 좌석을 예약하시겠습니까?");
scanf("%d", &ans1);

if (seat[ans1] == 0) {
seat[ans1-1] = 1;
printf("예약되었습니다.\n");
}
else printf("이미 예약된 자리입니다.\n");

}
return 0;
}*/

//배열 사용해서 최소값 찾기
/*
int main()
{
int a[10];
int min = 9999;

for (int i = 0; i < 10; i++) {
scanf("%d", &a[i]);
}

for (int i = 0; i < 10; i++) {
if (a[i] < min)min = a[i];
}

printf("%d", min);
return 0;
}*/


/*
void cnt(int a[])
{
for (int i = 0; i < 3; i++) {
a[i] = a[i] + 1;
}
}

int main()
{
int a[3] = { 1,2,3 };
cnt(a);
for (int i = 0; i < 3; i++) {
printf("%d ", a[i]);
}
}*/

//선택정렬
/*
int main()
{
int list[6] = { 5,3,8,1,2,7 };
int temp, min;

for (int i = 0; i < 5; i++) {
min = i;
for (int j = i + 1; j < 6; j++) {
if (list[j] < list[min]) {
min = j;
}
}

temp = list[i];
list[i] = list[min];
list[min] = temp;
}

for (int i = 0; i < 6; i++) {
printf("%d ", list[i]);
}

return 0;
}*/


//이진 탐색
/*
int main()
{
int list[6] = { 5,3,8,1,2,7 };
int min;
int temp;

for (int i = 0; i < 5; i++) {
min = i;
for (int j = i + 1; j < 6; j++) {
if (list[j] < list[min]) {
min = j;
}
}

temp = list[i];
list[i] = list[min];
list[min] = temp;
}

            //  m
//list 값 1 2 3 5 7 8
       // 0 1 2 3 4 5

int a; //우리가 탐색하고 싶은 수
scanf("%d", &a);
int low=0, high=5, mid;
while (low <= high) {
mid = (low + high) / 2;

if (a == list[mid]) {
printf("%d번째에 %d가 있다.", list[mid], a);
return 0;
}

else if (a > list[mid])low = mid + 1;
else high = mid - 1;
}
}*/

/*
//2차원 배열 입력 받는 방법
int main()
{
int a[3][5];

for (int i = 0; i < 3; i++) {
for (int j = 0; j < 5; j++) {
scanf("%d", &a[i][j]);
}
}

for (int i = 0; i < 5; i++) {
for (int j = 0; j < 5; j++) {
printf("%d ", a[i][j]);
}
printf("\n");
}
}*/


#include <math.h>
void a() {
float arr[10] = { 0 , };
float p_1 = 0;
float p_2 = 0;
float sum_1 = 0;
float sum_2 = 0;

for (int i = 0; i < 10; i++) {
scanf("%f", &arr[i]);
sum_1 = sum_1 + arr[i];
}
p_1= sum_1/10;//평균

for (int i = 0; i < 10; i++) {
 sum_2=sum_2+(arr[i] - p_1) * (arr[i] - p_1);
}
p_2 = sqrt(sum_2 / 10);
printf("평균 = %.6f\n", p_1);
printf("표준편차 = %.6f", p_2);

}

int main() {
a();
}
```
### 10주차 시험 코드
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

//1
/*
int result = 1;

int mul(int num)
{
result = result*num;
return result;
}

int main()
{
int num;
while (1) {
scanf("%d", &num);
if (num == 0)break;
mul(num);
}
printf("%d", result);
}*/

//2
/*
int sum(int num)
{
static int result = 0;
result = result + num;
return result;
}

int main()
{
int num;
int result;
while (1) {
scanf("%d", &num);
if (num == 999)break;
result = sum(num);
}
printf("%d", result);
return 0;
}*/

//3번
/*
int fac(int num)
{
if (num <= 1)return 1;
else return num * fac(num - 1);

}
int main()
{
int num;
scanf("%d", &num);
printf("%d", fac(num));
return 0;
}*/


//4번
/*
int main()
{
int num = 0;
int sum = 0;
int a[5] = { 0 };

for (int i = 0; i < 5; i++) {
scanf("%d", &num);
a[i] = num;
}

for (int i = 0; i < 5; i++) {
sum = sum + a[i];
}

printf("%d", sum / 5);
return 0;
}*/

//5번
/*
int main()
{
int max = 0;
int num;
int a[5];

for (int i = 0; i < 5; i++) {
scanf("%d", &num);
a[i] = num;
}

for (int i = 0; i < 5; i++) {
if (a[i] > max)max = a[i];
}
printf("%d", max);
return 0;
}*/


```

---

# 11주차 강의 내용

### 11주차 포인터 강의pdf
[attached course file]
- 11주차 실습 시험 코드

---

# 문자형 char를 1byte 이상 입력하고 싶을때

### Q. 문자형 char은 1바이트만 가능하다고 알고있는데 1바이트 이상을 입력하고 싶을때는 어떻게 해야할까요??
▶️ 문자형 char은 기본적으로 1바이트 크기를 가지지만, 여러 바이트로 된 문자열을 다루고 싶을 때는 문자열 배열을 활용할 수 있습니다! char a = 'a'는 a 하나만을 가지고 있지만 배열을 사용한다면 char a[6] = "apple" 과 같이 사용하여 여러 바이트로 된 문자열을 다룰 수 있습니다.

---

# 자료형 중 longlong이 사용되는 경우

### Q. longlong이라는걸 수업 시간에 배웠었는데 실제로 쓰이는 경우가 있나요?
▶️ C언어에서 longlong은 더 넓은 범위의 정수를 표현할때 사용합니다! 아마 1학년 1학기 수업에서는 longlong을 사용할 일이 별로 없지만 비트를 조작하거나 연산에서의 오버플로우 방지  또는 엄청 큰 수를 다룰때 사용될 수 있습니다!
6️⃣

---

# scanf와 scanf_s의 차이

### Q. scanf 와 scanf_s의 차이가 무엇인가요?
▶️ scanf와 scanf_s는 기능으로는 둘다 데이터의 입력을 받는 함수이지만 scanf_s는 scanf에서 보안을 개선한 함수라고 생각하시면 됩니다!

---

# 자료형 char에 하나의 철자를 쓴다면 왜 작은 따옴표를 사용해야하는지

### Q. 
1. char형에서 하나의 철자만 쓴다면 ' '을 사용해야한다고 하셨는데 이유가 궁금합니다
[image omitted: personal or temporary Notion asset]
▶️ c언어에서 '  ' (작은 따옴표)는 "문자"를 나타내는 의미이며 " "(큰 따옴표"는 문자열(문자들의 조합)을 나타내는 의미이기 때문에 간단하게 약속이라고 생각하시면 됩니다!

---

# 함수 return값에 따른 반환형 

[image omitted: personal or temporary Notion asset]
❓ 18번째 줄에서 왜 void로 하는지 
💡
함수에서 return 즉 main 함수로 반환해줄 것이 있을때 그 반환값의 형태에 따라 int, float, double, char 등이 들어갑니다. 만약 반환해줄 값이 없다면 void를 사용합니다.<br>위 코드에서는 multi라는 함수에 return으로 반환해주고 있는 값이 없기 때문에 void를 사용한다고 보시면 됩니다!
```javascript
int add(int a, int b)
{ 
return a+b;
}
int main()
{ 
int a, b; a=2; b=3; int sum = add(a,b); printf("%d",sum);
}
```
이 코드에서는 add 함수가 return으로 매개변수 a와 b를 합한 값을 main 중 변수 sum에 반환해주었죠??
이 코드와 위 코드의 차이를 보면 multi에는 return으로 main에 돌려주는 값이 없어 void를 사용한 것이며  add 함수에서는 return으로 main에 돌려주는 값이 있고 그 값은 정수형이기에 int를 사용한 것입니다.

---

# scanf 위치에 따른 출력값의 변화

[image omitted: personal or temporary Notion asset]
💡
코드 순서가 잘못되었습니다!
10줄에서 이미 b에 값을 넣어놓은 후에 scanf로 값을 받는다면
B는 a에 들어있던 쓰레기값으로 계산이 완료된채로 남아있겠죠?

---

# 반복문에서 count되는 값에 따른 출력값 변화

[image omitted: personal or temporary Notion asset]
❓ 왜 결과가 1단만 나오나요?
💡
 아마 안에있는 while문에서 j가 다 돌면 10이 되어있겠죠??
그렇다면 i가 2 이상이 되었을때는 계속 j가 10이기 때문에 안에있는 while문은 돌아가지 않습니다!

---

# 11주차 실습 시험 코드

### c언어 2024 11주차 - 1번
선택정렬(selection sort)은 정렬이 안 된 숫자들 중에서 최소값을 선택하여 배열의 첫번째 요소와 교환하는 정렬 방법 중 하나이다.
이 정렬은 최소값을 선택하지만 이 문제에서는 최대값을 선택하여 첫번째 요소와 교환하는 정렬을 작성하시오.
```c
int main()
{
int list[5] = { 0 };
int min, temp;
for (int i = 0; i < 5; i++) {
scanf("%d", &list[i]);
}
for (int i = 0; i < 4; i++) {
min = i;
for (int j = i + 1; j < 5; j++) {
if (list[j] > list[min]) {
min = j;
}
}
temp = list[i];
list[i] = list[min];
list[min] = temp;
}

for (int i = 0; i < 5; i++) {
printf("%d ", list[i]);
}
}
```
### 2번
A,B,C 총 3명의 친구들의 국어, 수학, 영어, 과학, 사회 총 5과목의 성적을 입력받은 뒤  세 친구의 평균을 구하여 가장 높은 평균을 출력하시오.
이떄 사용할 수 있는 변수의 개수는 총 3개이다. 
(for문에서 인덱스를 위해 사용하는 변수는 제외)
```c
int main()
{
int score[3][5] = { 0 };
int sum[3] = { 0 };

for (int i = 0; i < 3; i++) {
for (int j = 0; j < 5; j++) {
scanf("%d", &score[i][j]);
}
}

for (int i = 0; i < 3; i++) {
for (int j = 0; j < 5; j++) {
sum[i] += score[i][j];
}
sum[i] = sum[i] / 5;
}

int max = 0;
for (int i = 0; i < 3; i++) {
if (max < sum[i])max = sum[i];
}
printf("%d", max);
return 0;
}
```
### 3번
Palindrome 문자열은 앞에서부터 읽었을 떄와 뒤에서부터 읽었을 때 동일하다는 특징을 갖는다.
예를 들어 aba, aaa, abba 등은 palindrome 문자열이다.
입력받을 배열의 사이즈를 입력받은 후
사이즈만큼 배열을 입력 받아 
그 문자열이 palindrome이라면 1을 출력하고 아니라면 0을 출력하는 코드를 짜시오.
이때 문자열의 최대 크기는 10이다.
```c
int main()
{
int size = 0;
int num[10] = { 0 };
scanf("%d", &size);

for (int i = 0; i < size; i++) {
scanf("%d", &num[i]);
}

int cnt = 0;
for (int i = 0; i < size / 2; i++) {
if (num[i] == num[size - i-1])cnt++;
}

if (cnt == size / 2) {
printf("%d", 1);
}
else printf("%d", 0);
}
```
### 4번
문자 배열에 ‘@’가 들어오기 전까지 계속 문자를 받다가
‘@’가 들어온 후 지금까지 받았던 문자들을 거꾸로 출력하는 코드를 짜시오.
이때 문자열에는 ‘@’가 포함되어선 안 되며 문자열의 최대 크기는 100이다.
```c
int main()
{
char a[100] = { 0 };
int b = 0;
int i = 0;
while (1) {
scanf("%c", &a[i]);
if (a[i] == '@') {
a[i] = 0;
break;
}
i++;
}

for (int j = i; j >= 0; j--) {
printf("%c", a[j]);
}

return 0;
}
```
### 5번
문자열의 사이즈를 입력받은 후
그 사이즈 만큼 문자 배열에 문자를 입력받는다.
그 후 문자 배열에서 소문자인 문자는 대문자로 바꾸고
대문자인 문자는 소문자로 바꾸어 출력하시오.
이때 문자열 사이즈의 최대는 100이다.
```c
int main()
{
char s[10] = { 0 };

for (int i = 0; i < 10; i++) {
scanf("%c", &s[i]);
}

int change = 'A' - 'a';

for (int i = 0; i < 10; i++) {
if (s[i] >= 'a' && s[i] <= 'z') {
s[i] = s[i] + change;
}
else if (s[i] >= 'A' && s[i] <= 'Z') {
s[i] = s[i] - change;
}
}

for (int i = 0; i < 10; i++) {
printf("%c", s[i]);
}
return 0;
}
```
### 6번
swap함수는 함수의 매개변수의 값을 서로 바꾸어 저장하는 함수이다.
이때 전역변수와 static 변수를 사용하지 않으며 swap함수는 아무것도 return하지 않는 void 함수이다.
main함수에서 두 수를 입력받고 그 수를 swap함수를 통해 서로 바꾼 뒤 출력하는 코드를 짜시오.
```c
void swap(int* a, int* b)
{
int temp;
temp = *a;
*a = *b;
*b = temp;
}
int main()
{
int a, b;
scanf("%d %d", &a, &b);
swap(&a, &b);
printf("%d %d", a, b);
}
```
### 7번
swap 함수는 함수의 매개변수의 값을 서로 바꾸어 저장하는 함수이다.
이때 전역 변수와 static 변수를 사용하지 않으며 swap함수는 아무것도 return하지 않는 void함수이다.
main함수에서 데이터 타입이 정수인 두개의 배열을 입력 받아서 그 배열을 swap함수를 통해 서로 바꾼 뒤 출력하는 코드를 짜시오.
```c
void swap(int* num1, int* num2,int size)
{
int temp = 0;
for (int i = 0; i < size; i++) {
temp = num1[i];
num1[i] = num2[i];
num2[i] = temp;
}
}

int main()
{
int num1[100] = { 0 }, num2[100] = { 0 };
int size;
scanf("%d", &size);

for (int i = 0; i < size; i++) {
scanf("%d", &num1[i]);
}
for (int i = 0; i < size; i++) {
scanf("%d", &num2[i]);
}

swap(num1,num2,size);
for (int i = 0; i < size; i++) {
printf("%d ", num1[i]);
}
printf("\n");
for (int i = 0; i < size; i++) {
printf("%d ", num2[i]);
}
}
```
