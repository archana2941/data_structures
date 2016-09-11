# data_structures
#include<stdio.h>
#include<stdlib.h>
int main()
{
  int size;
  printf("\n enter size of queue");
  scanf("%d",&size);
  int queue[size];
  int front=-1,rear=-1;
  do
  {
    printf("\n enter 1: insert_element\n 2:delete\n 3:display\n 4:peek\n5:exit");
    scanf("%d",&option);
    switch(option)
    {
      case 1:
      `printf("enter element to insert");
       scanf("%d",&e);
       insert(e,size,queue);
       break;
      case 2:
       delete(queue);break;
      case 3:
       display(queue);break;
      case 4:
       peek(queue);break;
      
    }
  }
  while(option!=5);
  
}

void insert(int e,int size,int *queue)
{
  if( rear==size-1)
    printf("\n overflow");
  else if(front==-1 && rear==-1)
  {
    front=0;
    rear=0;
  }
  else
    rear++;
  queue[rear]=e;
}  

void delete(int *queue)
{
  if(front==-1 || front>rear)
    printf("underflow");
  else
  {
    int val=queue[front];
    front++;
    if(front>rear)
    {
      front=-1;rear=-1;
    }
    printf("\n %d",val);
    
  }
    
}

void display(int *queue)
{
  if(front==-1 || front>rear)
    printf("underflow");
  else
  {
    int i;
    for(i=front;i<=rear;i++)
    printf("\n%d ",queue[i]);
    
  }
}

void peek(int  *queue)
{
  if(front==-1 || front>rear)
    printf("underflow");
  else
    printf("\n%d",queue[front]);
}
