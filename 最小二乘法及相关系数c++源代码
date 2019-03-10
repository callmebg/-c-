#include <cmath>
#include <string>
#include <cstdio>
#include <cstdlib>
#include <iomanip>
#include <iostream>
using namespace std;

const int MAX = 10086;
double x[MAX], y[MAX];
double x_2[MAX], y_2[MAX], xy[MAX];
double sum_x, sum_y, sum_x_2, sum_y_2, sum_xy;
double ave_x, ave_y, ave_x_2, ave_y_2, ave_xy;
int num = 1; //数据组数
int fff;

void input();
void output();
double f(double num); //amazing 四舍五入

int main()
{
	string fuck1 = " 是 否 要 求 数 据 四 舍 五 入 (输入0代表不用，其它代表用)";
	string fuck2 = " 输 入 的 x 和 y 之 前 用 空 格 隔 开(输入完成后按ctrl+z并回车)";
    cout << fuck1 << endl;
    cin >> fff;
    cout << fuck2;
    input();
    output();
    system("pause");
    return 0;
}
void input()
{
    while (cin >> x[num] >> y[num])
    {
        x_2[num] = f(x[num] * x[num]);
        y_2[num] = f(y[num] * y[num]);
        xy[num] = f(x[num] * y[num]);

        sum_x += x[num];
        sum_y += y[num];
        sum_x_2 += x_2[num];
        sum_y_2 += y_2[num];
        sum_xy += xy[num];

        num++;
    }
    num--;
    ave_x = sum_x / num;
    ave_y = sum_y / num;
    ave_x_2 = f(sum_x_2 / num);
    ave_y_2 = f(sum_y_2 / num);
    ave_xy = f(sum_xy / num);
}
void output()
{
    cout << setw(5) << "No i"
         << setw(10) << "xi"
         << setw(10) << "yi"
         << setw(10) << "x_2 i"
         << setw(10) << "y_2 i"
         << setw(10) << "xy i";
    cout << endl;
    for (int i = 1; i <= num; i++)
    {
        cout << setw(5) << i
             << setw(10) << x[i]
             << setw(10) << y[i]
             << setw(10) << x_2[i]
             << setw(10) << y_2[i]
             << setw(10) << xy[i] << endl;
    }
    cout << setw(5) << "sum:"
         << setw(10) << sum_x
         << setw(10) << sum_y
         << setw(10) << sum_x_2
         << setw(10) << sum_y_2
         << setw(10) << sum_xy << endl;
    cout << setw(5) << "ave:"
         << setw(10) << ave_x
         << setw(10) << ave_y
         << setw(10) << ave_x_2
         << setw(10) << ave_y_2
         << setw(10) << ave_xy << endl;

    double a = (ave_xy - ave_x * ave_y) / (ave_x_2 - ave_x * ave_x);
    double b = ave_y - a * ave_x;
    cout << "a is " << a << endl;
    cout << "b is " << b << endl;

    double L_xy = f(ave_xy - f(ave_x * ave_y));
    double L_xx = f(ave_x_2 - f(ave_x * ave_x));
    double L_yy = f(ave_y_2 - f(ave_y * ave_y));

    cout << "L_xy is " << L_xy << endl;
    cout << "L_xx is " << L_xx << endl;
    cout << "L_yy is " << L_yy << endl;
    cout << "R is " << L_xy / sqrt(L_xx * L_yy) << endl;
    cout << " 方 程 是 ： y = " << a << "x + " << b << endl;
}
double f(double num)
{
    if (fff)
    {
        if (num - (int)num > 0.5)
            return (int)num + 1;
        else if (num - (int)num == 0.5)
        {
            //0.5时向偶数靠近
            if ((int)num & 1)
                return (int)num + 1;
            else
                return (int)num;
        }
        else
            return (int)num;
    }
    else
    {
        return num;
    }
}
/*

15 39.4
25.8 42.9
30 44.4
36.6 46.6
44.4 49.2

*/
