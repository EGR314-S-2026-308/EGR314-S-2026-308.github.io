---
title: Block Diagram, Protocol, and Message Structure
---

Draft *(Please Delete me)*

## 1. Team Block Diagram 

Below is a Block Diagram built of our project. In this figure we will show how we intend to connect our individual subsystems to build our project. We plan on mainly cominucating thorugh UART. However our HMI and Controler systems do also have a wireless comuncation protical. 





## 2. Sequence Diagram of Team Communication

This diagram will demonstrate how our commincation will travel through our system for each message type.

``` mermaid
sequenceDiagram
    actor User
    participant HMI
    User->>+SamB: Hello John, how are you?
    SamB->>+John:Hi
    Alice->>+John: John, can you hear me?
    John-->>-Alice: Hi Alice, I can hear you!
    John-->>-Alice: How are you doing?
    Alice->>+John: I can add as I want to Live
    loop Hello or condition (i<5, i++)
        SamB->>+John: Start loop line
        John->>Alice: We can talk like this too
        Alice->>+SamB: John is bothering me
    end
     alt (condition)
        Bob-->>Alice: Sending data
    else alt (condition)
        Bob-->>Alice: No data found
        else (HI I'm third case)
        Bob-->>Alice: Error 404
    end
    John->>-SamB: What's good
```

## 3. Message Types

We will mainly be utalizing UART comminication.