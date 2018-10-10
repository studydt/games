"""c

/*
计算24游戏
【设计要求】输入四个数通过加减乘除计算出24，显示计算过程，并提示成功信息。
*/
#include<iostream>
#include<Windows.h>
using namespace std;
int compute(int i, int j, int a[]) {
	int sum = 0;
	if (i == 0)
		sum = a[j] + a[j + 1];
	else if (i == 1)
		sum = a[j] - a[j + 1];
	else if (i == 2)
		sum = a[j] * a[j + 1];
	else if (i == 3 && a[j + 1] != 0)
		sum = a[j] / a[j + 1];
	return sum;
}
int main() {
	int a[4], sum = 0, sum1 = 0, sum2 = 0;
	cout << "Please enter four Numbers: a _ b _ c _ d =24" << endl;
	cout << "one:   ";
	cin >> a[0];
	cout << "two:   ";
	cin >> a[1];
	cout << "three: ";
	cin >> a[2];
	cout << "four:  ";
	cin >> a[3];
	for (int i = 0; i < 4; ++i) {

		sum = compute(i, 0, a);
		for (int j = 0; j < 4; ++j) {
			sum1=compute(j, 1, a);
			for (int k = 0; k < 4; ++k) {
				sum2=compute(k, 2, a);
				if ((sum+sum1+sum2)== 24) {
					cout << "yes";
					system("pause");
					return 0;
				}
			}
		}
	}
	cout << "not 24";
	system("pause");
	return 0;
}

"""
