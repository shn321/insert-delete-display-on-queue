# insert-delete-display-on-queue
#include<stdio.h>
#include<conio.h>
#define queue_size 5
int front=-1,rear=-1;
void enqueue(void);
void dequeue(void);
void display(void);
int QUEUE[queue_size];
void main()
{
 int choice;
 while(1)
 {
 printf("\n\n\t\t\t\t\t M A I N - M E N U");
 printf("\n\n\t\t\t\t\t 1.ENQUEUE ");
 printf("\n\n\t\t\t\t\t 2.DEQUEUE");
 printf("\n\n\t\t\t\t\t 3.DISPLAY");
 printf("\n\n\t\t\t\t\t 4.EXIT");
 printf("\n\n\t\t\t\t\t Enter Your Choice [1-4]");
 scanf("%d",&choice);
 switch (choice)
 {
 case 1:
 enqueue();
 break;
 case 2:
 dequeue();
 break;
 case 3:
 display();
 break;
 case 4:
 exit(0);
 default:
 printf("\n\n \t\t\t\t\t Invalid choice");
 break;
 }
 }
}
void enqueue()
{
 int item;
 if (rear==queue_size-1)
 {
 printf("\n\n\t\t\t\t\t Queue is full");
 getch();
 }
 else{
 printf("\n\n\t\t\t\t\t Enter value to insert");
 scanf("%d",&item);
 QUEUE[++rear]=item;
 if(front==-1)
 front++;
 }
}
void dequeue()
{
 int item;
 if((front==-1)||(front>rear))
 {
 printf("\n\n\t\t\t\t\t Queue is empty");
 }
 else{
 item=QUEUE[front];
 printf("\n\n\t\t\t\t\t%d s deleted from queue",item);
 front++;
 }
 getch();
}
void display()
{
 int i;
 if(front==-1||front>rear)
 printf("\n\n\t\t\t\t\t Queue is empty");
 else
 {
 system("cls");
 printf("Elements in queue are:");
 for(i=front;i<=rear;i++)
 printf("%d",QUEUE[i]);
}
getch();
}
