## Django Signals

Alright, let's explain Django signals in a really simple way:

Imagine you have a kitchen (which is your Django application), and you are cooking a meal. You have a toaster in this kitchen. Now, when you put bread in the toaster, you don't stand there watching it toast. Instead, you go about doing other things in the kitchen.

When the toast is ready, the toaster pops it up. This is like a signal - the toaster sends a "toast is ready" signal. In your Django app, when something important happens (like a user signing up), it's like the toast popping up. You can set up a part of your app to listen for this signal, and when it "hears" it (like you hearing the toaster pop), it can do something in response (like you taking out the toast and buttering it).

So, in short, Django signals are a way for different parts of your Django app to communicate with each other indirectly, like your toaster telling you the toast is ready without you having to watch it toast.

## Signals explained 
In Django, signals are a way for different parts of your web application to communicate with each other in a decoupled and modular way. They allow certain events or actions to trigger specific functions or code in other parts of your application without those parts needing to be directly aware of each other.

Here's a simple breakdown of how signals work in Django:

## Event Occurs:
Some event or action happens in your Django application. This could be anything, such as a new user registering, a record being saved to the database, or a user logging in.

## Signal Definition:
You define a signal for that event in your code. This signal is like a notification system, saying, "Hey, when this event happens, let other parts of the application know."

## Signal Handlers: 
You also define one or more signal handlers, which are functions or methods that should be executed when the signal is sent. These signal handlers are responsible for responding to the event.

## Connecting Signals: 
You connect the signal to its corresponding signal handler(s). This tells Django which functions should be called when the specified event occurs.

## Event Occurs, Signal Sent: When the event occurs, the signal is sent automatically by Django. It doesn't matter where or how the event happened; Django takes care of it.

Signal Handlers Execute: The connected signal handler(s) are executed in response to the event. They can perform various tasks, such as updating the database, sending emails, or performing any other action needed in response to the event.

Signals provide a way to keep your code modular and maintainable because different parts of your application can respond to events independently. They also help in decoupling components, as the sender of the signal doesn't need to know which specific functions will respond to it. This promotes a more organized and extensible codebase in Django applications.


## Signal Types 

#### Post Save

```
from django.db.models.signals import post_save


def profileUpdated(sender, instance, created, **kwargs):
    print('Profile Saved! Method triggered by signal event.')
    print('Sender:', sender)
    print('Intense:', instance)
    print('Is :', created)
    
post_save.connect(profileUpdated, sender=Profile)
```

## Configuring Signals 

Go to apps.py in the App Folder

