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
       2. when origin , destin greater than and equal to 0 , 
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
        if(origin>=0 || destin>=0 || origin<0 || destin<0)
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
