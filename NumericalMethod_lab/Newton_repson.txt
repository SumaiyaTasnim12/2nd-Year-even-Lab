#include<stdio.h>
#include<math.h>
#define F(x) (x*x*x -(3*x) + 1)
#define DF(x) (3*x*x -3)

int main()
{
    int i = 1;
    float fxn,dfxn,xn1,xn;
    float a = 0;
     xn = a;

    do
    {

        fxn = F(xn);
        dfxn = DF(xn);
        xn1 = xn - (fxn/dfxn);

        printf("step :%d  Xn : %.4f  f(xn): %.4f f'(xn) : %.4f  xn+1 : %.4f \n",i,xn,fxn,dfxn,xn1);

        xn = xn1;

        i++;
    }
    while(fabs(fxn) > 0.0001);


    printf("\n\napproximate root = %.4f\n",xn1);





}
