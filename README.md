# Bharath Simha Reddy Kothapeta
###### Takita Takita Kitchen and Bar
This  high-end fine dining restaurant has an extravagant **ambience** and stylish aura which reflects the modernity and glamorous style pf "Indian Royalty". It is my favourite restaurant mainly because they serve fresh food with the best ingredients available in the market. Moreover, I am fan of **Biryani**.

---

# Favorite Restaurant Dishes

1. Biryani.
2. Keema Samosa.
3. Chicken 65.

# Places to visit near the Restaurant

* Cine Planet.
* Fox Sagar.
* Raichandani Mall.

![mymedia](MyMedia.md)

---

# My Recommendation

My recommendation for anyone is books. Below table will include **Name**, **My Reason** and **Author**


| Name | Reason | Author |
| --- | --- | --- |
| Philosopher's Stone | Excellent plot twists and turns |  J. K. Rowling |  
| Discovery of India  |  The journey in The Discovery of India |  Jawaharlal Nehru | 
| Prisoner of Azkaban | Excellent plot twists and turns  | J. K. Rowling |

---

# Favorite Quotes

> "Be the change that you wish to see in the world."

> "Live as if you were to die tomorrow. Learn as if you were to live forever."

Author Name : *Mahatma Gandhi*

> *Mahatma Gandhi*

---

# Code Fencing

The below Python Code snippet is a simple implementation of a Thread pool using the Threading Module. The function f is a placeholder task and the Worker class is a subclass of Thread. It Executes tasks from a shared queue (self.q). The ThreadPool class represents the thread pool. It initializes a queue (self.q) with a specified number of worker threads (thread_num). The add_task method of the ThreadPool class is used to add tasks to the queue. The wait_complete method blocks until all tasks in the queue are processed. It uses the join method of the queue to wait for the queue to be empty. In the main block, a ThreadPool instance (pool) with 5 worker threads is created. Ten tasks (calling function f with argument 3) are added to the pool using the add_task method. The wait_complete method is then called to wait for all tasks to complete.


```
import threading
import time
from queue import Queue


def f(n):
    time.sleep(n)


class Worker(threading.Thread):
    def __init__(self, queue):
        super(Worker, self).__init__()
        self.q = queue
        self.daemon = True
        self.start()

    def run(self):
        while 1:
            f, args, kwargs = self.q.get()
            try:
                f(*args, **kwargs)
            except Exception as e:
                print(e)
            self.q.task_done()


class ThreadPool(object):
    def __init__(self, thread_num=10):
        self.q = Queue(thread_num)
        for i in range(thread_num):
            Worker(self.q)

    def add_task(self, f, *args, **kwargs):
        self.q.put((f, args, kwargs))

    def wait_complete(self):
        self.q.join()


if __name__ == '__main__':
    start = time.time()
    pool = ThreadPool(5)
    for i in range(10):
        pool.add_task(f, 3)
    pool.wait_complete()
    end = time.time() 

```

Click Here for : [ Snippet Link](https://code.pieces.app/collections/python)

