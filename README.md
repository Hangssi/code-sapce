# code-sapce

#include <stdio.h>
int main()
{
    int arr[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
    int k = 7;
    int sz = sizeof(arr)/sizeof(arr[0]);
    int left = 0;
    int right = sz - 1;
    
    while(left<=right)
    {
        int mid = (left + right) / 2;
    if(arr[mid]<k)
    {
        left = mid + 1;
    }
    else if(arr[mid]>k)
    {
        right = mid - 1;
    }
    else
    {
        printf("找到了,下标是: %d", mid);
        break;
    }
    if(left>right)
    {
        printf("找不到\n");
    }
    }
    return 0;
}
####


##猜数字游戏##
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
void menu()
{
   printf("####1. paly ####\n");
   printf("####0. exit  ####\n");
}
void game()
{
  int guess = 0;
  int ret = rand()%100+1;
  while(1)
    	{
    	  	printf("请猜数字:>");
    		  scanf("%d", &guess);
    		  if(guess>ret)
    			   {
        			 printf("太大了\n");
    			   }
    		  else if(guess<ret)
    			   {
        			 printf("太小了\n");
    			   }
    		  else
    			   {
        			 printf("猜到了\n");
           break;
    			   }
    	 }
}
int main()
{
    srand((unsigned int)time(NULL));
    int input = 0;
    do
    {
       menu();
       printf("请选择:>");
       scanf("%d", &input);
       switch(input)
        {
          case 1:
          	game();
          	break;
          case 0:
          	printf("退出游戏\n");
           break;
           default:
           printf("选择错误, 重新选择!\n");
           break;
        }
    }while(input);
    return 0;
 }

#####函数递归###
#include <stdio.h>

void print(unsigned int n)
	{
        if (n > 9)
    	{
            print(n/10);
        }
        printf("%d ", n % 10);
    }
int main(int argc, char** argv)
  {
    unsigned int num = 0;
    scanf("%u", &num);
    print(num);
    
    return 0;
  }

###不创建临时变量，求字符长度###
#include <stdio.h>
#include <string.h>


int my_strlen(char* str)
    {
        if(*str != '\0')
        {
            return 1 + my_strlen(str+1);
        }
        else
        {
            return 0;
        };
    }
    int main(int argc,char** argv) 
    {
    int len = my_strlen("abc");
    printf("%d", len);
    return 0;
  }

#####练习###
#include <stdio.h>
/*void Swap(int* px, int* py)
{
    int tmp = *px;
    *px = *py;
    *py = tmp;
    
}
int main(int argc, char** argv)
 {
     int a = 0;
     int b = 0;
     int c = 0;
     scanf("%d  %d %d", &a, &b, &c);
     if(a < b)
     {
         Swap(&a, &b);
     }
     if(a < c)
     {
         Swap(&a, &c);
     }
     if(b < c)
     {
         Swap(&b, &c);
     }
     printf("%d %d %d", a, b, c);
     return 0;
  }

int main(int argc,char** argv)
{
    int a = 0;
    int b = 0;
    int c = 0;
    scanf("%d %d", &a, &b);
    while(c = a%b)
    {
        a = b;
        b = c;
    }
    printf("%d", b);
    return 0;
}
int main(int argc,char** argv) 
{
    int i = 1;
    int count = 0;//计数
    for(int i = 1;i <= 100;i++) 
    {
        if(i % 10 == 9)//判断个位是不是9
        {
            printf("%d\n", i);
       	 count++;
        }
        if(i / 10 == 9)//判断十位是不是9
        {
            printf("%d\n", i);
       	 count++;
        }
    }
   printf("%d\n", count);
    return 0;
}

int main(int argc,char** argv) 
{
    int i = 0;
    double sum = 0;
    int flag = 1;
    for(int i = 1;i <= 100;i++) 
    {
        sum = sum + flag*(1.0 / i);
        flag = -flag;
    }
    printf("%lf\n", sum);
    
    return 0;
}
//###找出最大值
int main(int argc,char** argv) 
{
    
    int arr[10] = {0};
    int i = 0;
    for(i = 0;i < 10;i++) 
    {
        scanf("%d", &arr[i]);
    }
    int max = arr[0];
    for(int i = 1;i < 10;i++) 
    {
        if(max < arr[i])
        {
            max = arr[i];
        }
    }
    printf("%d\n", max);
    return 0;
}

void chen(int n)
{
    int i = 0;
    
    for(i = 1;i <= n;i++) 
    {
        int j = 0;
        for(j = 1;j <= i;j++) 
        {
            printf("%d*%d=%-2d ", i, j, i * j);
            
        }
       printf("\n");
    }
}
int main(int argc,char** argv) 
{
    int n = 0;
    scanf("%d", &n);
    chen(n);
    return 0;
    
    
}*/

#####冒泡排序####
#include <stdio.h>
void bubble_sort(int* arr, int sz)//数组形式传参arr []
{
    int i= 0;
    for(int i = 0;i < sz;i++) 
    {
        int j = 0;
        for(int j = 0;j < sz-1-i;j++) 
        {
            if(arr[j] > arr[j+1])
            {
                int  tmp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = tmp;
            }
        }
    }
}
int main(int argc, char** argv)
 {
     
     int arr[ ] = {9,8,7,6,5,4,3,2,1,0};
     int sz = sizeof(arr)/sizeof(arr[0]);
     for(int i = 0;i < sz;i++) 
     {
         scanf("%d", &arr[i]);
     }
         
     bubble_sort(arr, sz);
     int i = 0;
     
     for(int i = 0;i < sz;i++) 
     {
         printf("%d ", arr[i]);
     }
     return 0;
 }
