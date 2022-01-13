# The-circle-of-system
/*#include<stdio.h>
int main()
{
	int i = 1;
	while (i <= 10)
	{
		if (i == 5)
			//break;//此时循环停止，跳出该循环圈
		continue;//此时死循环i永远等于5，后面代码不再继续，直接跳转到该循环的判断语句
		printf("%d", i);
		i++;
	}
	return 0;
}*/
/*#include<stdio.h>
int main()
{
	//int ch = getchar();//输入一个字符赋给ch中
	//putchar(ch);//输出一个字符
	//printf("%c\n", ch);
	/*int ch = 0;
	//ctrl+z;
	//EOF - end of file->-1 文件结束标志
	while ((ch = getchar())!=EOF)
	{
		putchar(ch);
	}
	int ret = 0;
	char password[20] = { 0 };
	printf("请确认密码:>");
	scanf("%s", password );//输入密码，并存放在password数组中12345 ABCD空格前的五个数字读取到scanf中
	//缓冲区还剩下一个'\n'
	//读取下一个'\n'
	while ((getchar()) != '\n')//直到读取到最后的'\n'
	{
		;
	}
	printf("请确认(Y/N):>");
	ret = getchar();
	if (ret == 'Y')
	{
		printf("确认成功\n");
	}
	else
	{
		printf("放弃确认\n");
	}
	return 0;
}*/
/*#include<stdio.h>
//从键盘上输入a(0 < a < 10)和n，计算a + aa + aaa + ... + aa...aaa(n个a)的值。
//	例：
//（1）输入：2 5  输出：24690
//（2）输入：9 9  输出：1111111101
int main()
{
	int a,n,c,b;	
	scanf("%d%d", &a, &n);
      c = a;
	  b = 0;
	for (int i = 1; i <= n; i++)
	{	
		b += c;
		c = 10 *c +a;
	
	}
	printf("%d", b);
	return 0;
}*/

/*#include<stdio.h>
//从键盘上输入正整数n，求1!+ 2!+ ... + n!的值。
//例：
//（1）输入：1 输出：sum = 1
//（2）输入：10 输出：sum = 4037913
//（3）输入：20 输出：sum = 2561327494111820313//此数的单位已大于十位不能用int型定义该变量用long long型
int main()
{

	int n;
	scanf("%d", &n);
	 long long int sum = 0;
	long long int s = 1,i;
	for ( i = 1; i <= n; i++)
	{
		sum = sum + s;
		s = s * (i + 1);
	}
	printf("%lld", sum);
	return 0;
}*/
// 1.for循环的初始化、调整、判断都可以省略
//但是若判断语句一旦省略，则其判断条件就是恒为正；
/*#include<stdio.h>
int main()
{
	int i = 0;
	do
	{
		if (i == 5)
			//break;
			continue;//死循环
		printf("%d ", i);
		i++;
	} 
	while (i <= 10);
	return 0;
}*/

/*#include<stdio.h>
int main()
{
	int k = 7;
	int arr[10] = { 1,2,3,4,5,6,7,8,9,10 };
	int a = sizeof(arr) / sizeof(arr[0]);//计算数组元素个数
	int left = 0;
	int right = a - 1;
	while (left <= right)//只有当左下标小于等于右下标时即中间有元素时才可进行查找
	{   //折半查找算法
		int mid = (left + right) / 2;
		if (arr[mid] > k)
		{
			right = mid - 1;
		}
		else if (arr[mid] < k)
		{
			left = mid + 1;
		}
		else
		{
			printf("找到了，下标是：%d", mid);
			break;
		}
	}
	return 0;
}*/
/*#include<stdio.h>
//水仙花数是指一个3位数，其各位数字立方和等于该数本身。
//例：153 = 1 * 1 * 1 + 5 * 5 * 5 + 3 * 3 * 3
//输出所有的水仙花数，每输出一个水仙花数后再输出一个空格进行间隔（共4个水仙花数）。
int main()
{
	int gw, sw, bw;
	for (int a = 100; a <= 999; a++)
	{
        gw = a % 10;
	    sw = a / 10 % 10;
	    bw = a / 100 % 10;
		if (a == gw * gw*gw + sw * sw*sw + bw * bw*bw)
		printf("%d ", a);
	}
	return 0;
}*/
/*#include<stdio.h>
//一个球从100m高度自由落下，每次落地后反跳回原高度的一半，再落下，再反弹。求它在第10次落地时，共经过多少米，第10次反弹多高。
//输出：sum = 299.61, h = 0.10
//求出：求它在第n次落地时共经过多少米，第n次反弹多高如何做？
int main()
{
	float sum = 0;
	float h = 100;
	int n;
	scanf("%d", &n);
	for (int i = 1; i <= n; i++)
	{
		if(i==1)
		{ 
		sum = sum + h;
		h = h / 2;
		}
		else
		{    
			sum = sum + 2 * h;
            h = h / 2;
		}
	}
	printf("sum=%.2lf,h=%.2lf", sum, h);
	return 0;
}*/
//猴子吃桃问题：猴子第1天摘了若干个桃子，当即吃了一半，还不过瘾，又多吃了一个。
//第2天早上又将剩下的桃子吃掉了一半，又多吃了一个。以后每天早上都吃了前一天剩下的一半零一个。
//到第n天早上想吃时，只剩下一个桃子了。求第1天共摘了多少个桃子。从键盘上输入n
/*#include<stdio.h>
int main()
{
	int a = 1,n;
	scanf("%d", &n);
	for (int i = 2; i <= n; i++)
	{
      a = (a + 1) * 2;//逆向思维 第一天为1个 第二天为（1+1）*2 第三天为（4+1）*2
	}
	printf("%d", a);
	return 0;
}*/
//#include<stdio.h>
////公鸡5元一只，母鸡3元一只，小鸡1元三只。给你100元钱，买100只鸡回来，问如何买？
////gj 0-20//mj 0-33//xj 0-99找出该变量的范围
//int main()
//{
//	int hens,cocks,chickens;
//	for (hens = 0; hens <20; hens++)
//	{
//		for (cocks = 0; cocks < 33; cocks++)
//		{
//			chickens = 100 - hens - cocks;
//			if (chickens % 3 == 0 && 5 * hens + 3 * cocks + 1 * chickens / 3 == 100)
//			{
//				printf("cocks:%d,hens:%d,chickens:%d\n", cocks, hens, chickens);
//			}
//			/*for (chickens = 0; chickens < 99; chickens += 3)
//			{
//				if (hens + cocks + chickens == 100 && 5 * hens + 3 * cocks + 1 * chickens / 3==100)
//					printf("cocks:%d,hens:%d,chickens:%d\n", cocks, hens, chickens);
//			}*///三重循环
//		}
//
//	}
//	return 0;
//}
//#include<stdio.h>
//从键盘上输入一个正整数n，它是奇数，计算1与n之间所有奇数的和：1 + 3 + 5 + 7 + ... + n
//例：
//（1）输入：1  输出：sum = 1
//（2）输入：3  输出：sum = 4
//（3）输入：99 输出：sum = 2500
//int main()
//{
//	int a = 0;
//	int sum = 1,n;
//	scanf("%d", &n);
//	/*while (sum <= n)
//	{
//		a += sum;
//		sum = sum + 2;
//    }*/
//	for (int i = 1; i <= n; i+=2)
//	{
//		a += sum;
//		sum += 2;
//	}
//	printf("sum=%d", a);
//	return 0;
//}
/*#include<stdio.h>
//用do...while语句计算1 + 2 + 3 + ... + n的值
int main()
{
	int sum = 0, n;
		scanf("%d", &n);
		int i = 1;
		do
		{
			sum += i;
			i++;
		} //先无条件地执行循环体，然后判断循环条件是否成立
	    while ( i <= n);
		printf("sum=%d", sum);
	return 0;
}*/










