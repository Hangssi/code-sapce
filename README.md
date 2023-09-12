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
    srand((unsigned int)time(NULL ));
    int  input = 0;
    
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
