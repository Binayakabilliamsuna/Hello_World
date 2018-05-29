//*this is a stack operation program*//


#include<stdio.h>
#include<conio.h>
#include<stdlib.h>
int stack[50],tos=-1,size;
void main()
{
    int choice,ele,con;
    printf("Enter the stack size: ");
    scanf("%d",&size);
    do
    {
        system("cls");
        printf("\n1.push\n2.pop\n3.Display\n4.peep\n5.update\n6.exit\n");
        printf("Enter your choice:\n");
        scanf("%d",&choice);
        switch(choice)
        {
        case 1:
            printf("Enter the number you want to push:\n");
            scanf("%d",&ele);
            push(ele);
            break;
        case 2:
            pop();
            break;
        case 3:
            display();
            break;
        case 4:
            peep();
            break;
        case 5:
            update();
            break;
        case 6:
            exit(0);
        default:
            printf("\ninvalid position");
        }
        printf("\nyou want to continue stack[1-yes::0-No]: ");
        scanf("%d",&con);
    }while(con==1);
    getch();
}
void push(int ele)
{
    if(tos==size-1)
        printf("\nstack overflow");
    else
    {
        tos++;
        stack[tos]=ele;
    }
}
void pop()
{
    int ele;
    if(tos==-1)
        printf("\nstack underflow");
    else
    {
        ele=stack[tos];
        tos--;
        printf("\nThe poped element is: %d",ele);
    }
}
void display()
{
    int i;
    if(tos==-1)
        printf("\nstack is empty");
    else
    {printf("\nstack is:\n");
    for(i=tos;i>=0;i--)
        printf("%d\n",stack[i]);
    }
}
void peep()
{
    int ele,pos,k;
    printf("Enter the position you want to peep[0-%d]: ",tos+1);
    scanf("%d",&pos);
    k=(tos-pos)+1;
    if(k>tos||k<0)
        printf("\ninvalid position");
    else
    {
        ele=stack[k];
        printf("\nThe peep element is: %d",ele);
    }
}
void update()
{
    int pos,k,ele;
    printf("enter the position you want to update: ");
    scanf("%d",&pos);
    k=(tos-pos)+1;
    if(k>tos||k<0)
        printf("\nNo element in the stack");
    else
    {
    printf("\nEnter the element you want to input: ");
    scanf("%d",&ele);
        stack[k]=ele;
    }
}
