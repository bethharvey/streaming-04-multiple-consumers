# streaming-04-multiple-consumers

* Beth Harvey
* Streaming Data
* Module 4
* September 10, 2023

### Requirements
`python3 -m venv .venv`
`source .venv/bin/activate`
`python3 -m pip install pika`


The goal of this project is to use RabbitMQ to send messages/tasks from a single producer to multiple consumers. This is based on the RabbitMQ tutorial linked in the "Read" section below.

> Use RabbitMQ to distribute tasks to multiple workers

One process will create task messages. Multiple worker processes will share the work. 


## Before You Begin

1. Fork this starter repo into your GitHub.
1. Clone your repo down to your machine.
1. View / Command Palette - then Python: Select Interpreter
1. Select your conda environment. 

## Read

1. Read the [RabbitMQ Tutorial - Work Queues](https://www.rabbitmq.com/tutorials/tutorial-two-python.html)
1. Read the code and comments in this repo.

## RabbitMQ Admin 

RabbitMQ comes with an admin panel. When you run the task emitter, reply y to open it. 

(Python makes it easy to open a web page - see the code to learn how.)

## Execute the Producer

1. Run emitter_of_tasks.py (say y to monitor RabbitMQ queues)

Explore the RabbitMQ website.

## Execute a Consumer / Worker

1. Run listening_worker.py

Will it terminate on its own? How do you know? 
    No: When it starts it says "To exit press CTRL+C and the terminal does not return to an input line until you end the process.

## Ready for Work

1. Use your emitter_of_tasks to produce more task messages.

## Start Another Listening Worker 

1. Use your listening_worker.py script to launch a second worker. 

Follow the tutorial. 
Add multiple tasks (e.g. First message, Second message, etc.)
How are tasks distributed? 
    They alternate between the two workers.
Monitor the windows with at least two workers. 
Which worker gets which tasks?
    Worker 1 gets odd tasks, and worker 2 gets even tasks.


## Reference

- [RabbitMQ Tutorial - Work Queues](https://www.rabbitmq.com/tutorials/tutorial-two-python.html)


## Screenshot

See a running example with at least 3 concurrent process windows here:

![One producer with multiple consumers](./multiple_processes_v2.png)
