# STACK
CODE OF STACK(DATASTRUCTURE)
#include<stdio.h>
#include<stdlib.h>
#define size 100
static int top=-1;
int stack[size];
int push(int);
int pop();
int peek();
int search();
int display();
int main()
{
	int cho,maxsize;
	printf("Enter the maxsize of the stack: ");
	scanf("%d",&maxsize);
	while(cho!=6)
	{
		printf("List of Operations in Stack:\n1. PUSH Element\n2. POP Element\n3. PEEK Element\n4.Search Element\n5. Display\n6. Exit\n");
		printf("Enter Your Choice: ");
		scanf("%d",&cho);
		switch(cho)
		{
			case 1:
				push(maxsize);
				break;
				case 2:
					pop();
					break;
					case 3:
						peek();
						break;
						case 4:
							search();
							break;
							case 5:
								display();
								break;
								case 6:
									exit(0);
									break;
									default:
										printf("Wrong Choice entered, Please press(1/2/3/4/5/6) according to your choice\n");
		}
	}
}
int push(int maxsize)
{
	int item;
	if(top==maxsize-1)
	printf("The Stack is in Overflow Condition, can't enter data.\n");
	else
	{
		printf("Enter Element: ");
		scanf("%d",&item);
		top++;
		stack[top]=item;
		printf("%d element entered in the Stack\n",stack[top]);		
	}	
}
int pop()
{
	if(top==-1)
	printf("The Stack is in Underflow Condition, can't delete data.\n");
	else
	{
		printf("%d element deleted from the Stack\n",stack[top]);
		top--;		
	}		
}
int peek()
{
	if(top==-1)
	printf("The Stack is in Underflow Condition, no element is there to show\n");
	else
	{
		printf("%d element is the peek element in the Stack\n",stack[top]);	
	}	
}
int search()
{
	int key,i,flag;
	if(top==-1)
	printf("The Stack is in Underflow Condition, no element is there to search\n");
	else
	{
		printf("Enter the key element: ");
		scanf("%d",&key);
		for(i=top;i>=0;--i)
		{
			if(key==stack[i])
			{
				flag=0;
			}
			else
			flag = 1;
		}
		if(flag==1)
		printf("Element is not present in the stack\n");
		else
		printf("Element is found in the stack\n");	
	}
}
int display()
{
	int i;
	if(top==-1)
	printf("The Stack is in Underflow Condition, no element is there to search\n");
	else
	{
		printf("Elements in the Stack is: ");
		for(i=top;i>=0;--i)
		{
			printf("%d ",stack[i]);
		}
		printf("\n");	
	}	
}
