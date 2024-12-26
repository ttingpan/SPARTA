# [Unreal 1/2기] CH 2 간단한 프로그래밍  구현 1번 과제
## 필수 기능
- 숫자를 입력 받아 배열에 저장하고 이들의 합계와 평균을 계산해서 출력하는 기능
- 숫자를 입력 받는 공간은 배열을 활용
- 합과 평균을 구하는 동작은 각각 함수를 구현

```c#
#include <iostream>

using namespace std;

// 입력 숫자들의 합
int Sum(int arr[], int size)
{
	int s = 0;
	for (int i = 0; i < size; i++)
	{
		s += arr[i];
	}

	return s;
}

// 입력 숫자들의 평균
double Avg(int arr[], int size)
{
	return (double) Sum(arr, size) / size;
}

int main()
{
	// 입력 받을 숫자의 총 수;
	int n = 0;

	cout << "입력할 숫자의 총 개수(양의 정수) 입력 : ";
	cin >> n;
	cout << endl;

	// 0과 음수 입력 방지
	if (n <= 0)
	{
		cout << "양의 정수를 입력하세요.";
		return 1;
	}

	// 입력 받은 숫자 배열
	// 배열의 크기를 상수가 아닌 변수로 지정하기 위해
	// 동적 배열 사용
	int* numbers = new int[n];

	for (int i = 0; i < n; i++)
	{
		// 입력 받은 숫자 저장할 임시 변수
		int number;
		cout << i + 1 << " 번째 수 입력 : ";
		cin >> number;

		numbers[i] = number;
	}

	cout << "입력한 숫자들의 합 : " << Sum(numbers, n) << endl;
	cout << "입력한 숫자들의 평균 : " << Avg(numbers, n) << endl;

	return 0;
}
```
