#include <stdio.h>
#include <math.h>
 int f  (double a, double b, double c);
 
int main()
{
	int d;
	double a, b, c, m, s, area;
	scanf("%lf %lf %lf",&a,&b,&c);
	d = f(a,b,c);
	if (d == 0)
	{
		printf("These sides do not correspond to a valid triangle");
	}
	else
	{
		s = (a + b + c) / 2;
		m = s * (s-a) * (s-b) * (s-c);
		area = sqrt(m);
		printf("area = %.2f;",area);
		printf(" perimeter = %.2f",2*s);
	}
	return 0;

}
int f(double a, double b, double c)
{
	int flog = 0;
	if (a + b > c)
	{
		flog++;
	}
	if (a + c > b)
	{
		flog++;
	}
	if (b + c > a)
	{
		flog++;
	}
	if (flog == 3)
	{
		return 1;
	}
	else
	{
		return 0;
	}
}
