
# Queue Using Array in C

Implementation of Queue Data Structure in C using Arrays.


## Creation of Structure


    struct queue{
        int rear;
        int front;
        int size;
        int *arr;
    };

## To check if Queue is Empty or Full
    int isFull(struct queue *q){
        if(q->rear >= (q->size)-1){
            return 1;
        }
        else{
            return 0;
        }
    }
    int isEmpty(struct queue *q){
        if(q->front == q->rear){
            return 1;
        }
        else{
            return 0;
        }
    }
## Enqueue-Function
    void enqueue(struct queue *q, int data){
        if(isFull(q) == 1){
            printf("Queue Overflow");
        }
        else{
            q->rear += 1;
            q->arr[q->rear] = data;
        }
    }

## Dequeue-Function
    int dequeue(struct queue *q){
        int a = -1;
        if(isEmpty(q)==1){
            printf("Queue Underflow");
        }
        else{
            int a = q->arr[q->front + 1];
            q->front += 1;
            return a;
        }
    }
## Display Queue and Main function
    void display(struct queue *q){
        for(int i=(q->front+1); i <= (q->rear) ; i++){
        printf("%d  ",q->arr[i]);
        }
    }

    int main(){
        struct queue *q = (struct queue *)malloc(sizeof(struct queue));
        q->size = 10;
        q->rear = q->front = -1;
        q->arr = (int *)malloc(q->size * sizeof(int));

        enqueue(q,10);
        enqueue(q,20);
        enqueue(q,30);
        enqueue(q,40);

        display(q);

        int a = dequeue(q);
        printf("\n");
        display(q);

        return 0;
    }
## Authors

- [@vaibhav-INDIE](https://github.com/vaibhav-INDIE)

