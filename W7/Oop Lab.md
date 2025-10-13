# OOP in Python
## 1. Extending Stack class behavior
```python
class Stack:
    def __init__(self):
        self.__stack_list = []

    def push(self, val):
        self.__stack_list.append(val)

    def pop(self):
        return self.__stack_list.pop()

class CountingStack(Stack):
    def __init__(self):
        super().__init__()           
        self.__pop_counter = 0       

    def pop(self):
        val = super().pop()          
        self.__pop_counter += 1      
        return val

    def get_counter(self):
        return self.__pop_counter

if __name__ == "__main__":
    stack = CountingStack()

    for i in range(100):
        stack.push(i)

    for i in range(100):
        stack.pop()

    print("Number of pops:", stack.get_counter())  # Should print 100
```
## 2a. Implementing a queue class from scratch (intermediate difficulty)
```python
class QueueError(Exception):  
    pass

class Queue:
    def __init__(self):
        self._storage = []  

    def put(self, elem):
        self._storage.insert(0, elem)  
    def get(self):
        if not self._storage:
            raise QueueError("Queue is empty")
        return self._storage.pop()     
        
que = Queue()
que.put(1)
que.put("dog")
que.put(False)

try:
    for i in range(4):
        print(que.get())
except QueueError:
    print("Queue error")
```
## 2b. Extending a Queue class capability in part 2a (intermediate difficulty)
```python
# Custom exception
class QueueError(Exception):
    pass

# Base Queue class
class Queue:
    def __init__(self):
        self._storage = []

    def put(self, elem):
        self._storage.insert(0, elem)

    def get(self):
        if not self._storage:
            raise QueueError("Queue is empty")
        return self._storage.pop()

# Extended Queue class with isempty method
class SuperQueue(Queue):
    def isempty(self):
        """Return True if the queue is empty, False otherwise."""
        return len(self._storage) == 0

# Test code
que = SuperQueue()
que.put(1)
que.put("dog")
que.put(False)

for i in range(4):
    if not que.isempty():
        print(que.get())
    else:
        print("Queue empty")
```
## 3. Class Timer
```python
def format_time(h, m, s):
    return f"{h:02d}:{m:02d}:{s:02d}"

class Timer:
    def __init__(self, hours=0, minutes=0, seconds=0):
        self.__hours = hours
        self.__minutes = minutes
        self.__seconds = seconds

    def __str__(self):
        return format_time(self.__hours, self.__minutes, self.__seconds)

    def next_second(self):
        self.__seconds += 1
        if self.__seconds >= 60:
            self.__seconds = 0
            self.__minutes += 1
            if self.__minutes >= 60:
                self.__minutes = 0
                self.__hours += 1
                if self.__hours >= 24:
                    self.__hours = 0

    def prev_second(self):
        self.__seconds -= 1
        if self.__seconds < 0:
            self.__seconds = 59
            self.__minutes -= 1
            if self.__minutes < 0:
                self.__minutes = 59
                self.__hours -= 1
                if self.__hours < 0:
                    self.__hours = 23

timer = Timer(23, 59, 59)
print(timer)        
timer.next_second()
print(timer)        
timer.prev_second()
print(timer)       
```
## 4. Weeker Class
```python
class WeekDayError(Exception):
    pass

class Weeker:
    __days = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']

    def __init__(self, day):
        if day not in Weeker.__days:
            raise WeekDayError(f"Invalid day: {day}")
        self.__index = Weeker.__days.index(day)  

    def __str__(self):
        return Weeker.__days[self.__index]

    def add_days(self, n):
        self.__index = (self.__index + n) % 7  

    def subtract_days(self, n):
        self.__index = (self.__index - n) % 7  

try:
    weekday = Weeker('Mon')
    print(weekday)          
    weekday.add_days(15)
    print(weekday)          
    weekday.subtract_days(23)
    print(weekday)          
    weekday = Weeker('Monday')  
except WeekDayError:
    print("Sorry, I can't serve your request.")
```
