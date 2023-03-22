# Mod17
# Topological Sort
```
/*
creating graph
 
 variables : 
 i - for loop , max_edge - store value , origin , destin - user ip. 
1. getting n from user - n : number of vertices
2. max_edge = no of vertices * (no of vertices -1)
 
3. for loop from 1 to max_edge - 
   {
       user ip - origin destin
       1. when origin and destin is -1 break ;
       2. when origin , destin greater than and equal to n , 
       when origin , destin lesser than 0 - the edge is invalid and drecrement i ;
       3. matrix with origin destin is equal to 1
   }
*/
```
```
void create_graph()
{
    int i,max_edge,origin,destin;
    scanf("%d",&n);
    max_edge=n*(n-1);
    for(i=1;i<=max_edge;i++)
    {
        scanf("%d%d",&origin,&destin);
        if(origin==-1 && destin==-1)
        {
            break;
        }
        if(origin>=n || destin>=n || origin<0 || destin<0)
        {
            printf("Invalid edge\n");
            i--;
        }
        else
        {
            adj[origin][destin]=1;
        }
    }
}
```
```
/*
Topological Sort

inserting queue (vertex)

variables using - rear , MAX , front , queue[] , vertex
1. check overflow - 
          when rear is equal to max - 1
2. else 
{
    1. when queue is empty - front is 0; 
    queue is empty when it is equal to -1
       
    2. else 
    rear = ?   queue[rear] = ?
    rear is equal to rear + -1
    queue[rear] is vertex 
}
*/
```
```
void insert_queue(int vertex)
{
    if(rear == MAX-1)
    {
        printf("Queue Overflow");
    }
    else
    {
        if(front==-1)
        {
            front =0;
        }
        else
        {
            rear=rear+1;
            queue[rear]=vertex;
        }
    }
}
```
```
/*

delete queue

1 . declare item have to b deleted . 
2 . check underflow 
    when front is equal to -1 or front greater than rear 
    print and exit(1);
3 . else
    assign variable = front of queue
    inc front
    return variable . 

*/
```
```
int delete_queue()
{
    int del_item;
    if(front==-1||front>rear)
    {
        printf("Queue underflow");
        exit(1);
    }
    else
    {
        del_item=queue[front];
        front=front+1;
        return del_item;
    }
}
```
```
/*
empty

queue is empty when front is equal to -1 or 
front is greater than rear
```
```
int isEmpty_queue()
{
    if(front==-1||front>rear)
    {
        return  1;
    }
    else
    {
        return  0;
    }
}
```
```
indegree

1 . declare variable i and in_deg
2 . assign in_deg is 0
3 . for loop from 0 to n
    {
        when matrix of i , v is 1
        increment in_deg;
    }
4 . return in_deg;
*/
```
```
int indegree(int v)
{
    int i,in_deg=0;
    for(i=0;i<n;i++)
    {
        if( adj[i][v]==1)
        {
            in_deg++;
        }
    }
    return in_deg;
}
```
