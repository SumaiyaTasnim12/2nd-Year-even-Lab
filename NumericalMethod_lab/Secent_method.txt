#include<stdio.h>
#include<math.h>
//#define f(x) ((x*x*x)-(2*x)-5)
#define f(x) ((x*exp(x))-1)
int main()
{

    int i=0;
    float x0,x1,x2,fx0,fx1,fx2;
    printf("Enter Two Initial value ");
    scanf("%f%f",&x0,&x1);

    do
        {
            fx0 = f(x0);
            fx1 = f(x1);

         // x2 = x1-((x1-x0)*f(x1))/(f(x1)-f(x2));
          x2 = x1-(f(x1)*(x1-x0))/(f(x1)-f(x0));

            fx2 = f(x2);

            fx0 = fx1;
            fx1 = fx2;

            x0 = x1;
            x1 = x2 ;
            i++;

        printf("Iteration %d X%d =%.3f  X%d =%.3f X%d =%.3f\n",i,i-1,x0,i,x1,i+1,x2);
        }while(fabs(fx2)>.001);

        printf("Root %.3f",x2);

}
