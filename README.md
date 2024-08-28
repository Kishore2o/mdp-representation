# MDP REPRESENTATION

## AIM:
The aim of this experiment is to create a Markov Decision Process (MDP) representation and implement it in Python to model the decision-making process in a medical treatment scenario.

## PROBLEM STATEMENT:

### Problem Description
The problem involves managing the treatment of patients who can be in one of four states: Sleeping,Wakeup,Reading, Playing and Cooking. The objective is to determine whether to check patient is able to Cook.

### State Space
State 0: Sleeping State 1: Wakeup State 2: Reading State 3: Playing State 4: Cooking

{Sleeping,Wakeup,Reading,Playing,Cooking} -> {0, 1, 2,3,4}

### Sample State
State: Sleeping -> 0 (The patient is Sleeping, represented numerically as 0.)

### Action Space
Action 0: Sleeping Action 1: Wakeup etc....

{Treat, Not Treat} -> {0, 1}

### Sample Action

Action: Wakeup Treat -> 1 (The action taken is to Waking up the patient, represented numerically as 1.)



### Reward Function
R = { +1 , if the patient state is changed to Cook state or not, otherwise -1}

Transition to Cook state: +1 Staying sick : -1 Terminal states: No reward

### Graphical Representation

![image](https://github.com/user-attachments/assets/8133e1e2-ce72-4d89-a5ae-1f089d8bee90)

## PYTHON REPRESENTATION:
```
p = {
    0:{
        1:[(0.6,1,0.0,False),(0.4,0,0.0,False)],
        0:[(0.6,0,0.0,False),(0.4,1,0.0,False)]
    },
    1:{
        1:[(0.6,2,0.0,False),(0.4,0,0.0,False)],
        0:[(0.6,0,0.0,False),(0.4,2,0.0,False)]
    },
    2:{
        #lef
        2:[(0.6,1,0.0,False),(0.4,2,0.0,False)],
        #righ
        1:[(0.6,4,1,True),(0.4,2,0.0,False)],
        #up
        0:[(0.6,3,0.0,True),(0.4,2,0.0,False)]
    },
    3:{
        1:[(0.6,2,0.0,False),(0.4,3,0.0,False)],
        0:[(0.6,3,0.0,True),(0.4,2,0.0,False)]
        
    },
    4:{
        1:[(0.6,4,1,True),(0.4,2,0.0,False)],
        0:[(0.6,2,0.0,False),(0.4,4,1,True)]
    }
}
print(p)
```

## OUTPUT:

![image](https://github.com/user-attachments/assets/5e21f233-6447-42d1-96dd-a7aa8398716d)


## RESULT:
The Markov Decision Process (MDP) has been successfully represented using Python dictionaries. Each state-action pair contains information about possible transitions, transition probabilities, associated rewards, and whether the next state is terminal or not. This representation can be used for further analysis and decision-making algorithms such as reinforcement learning.

