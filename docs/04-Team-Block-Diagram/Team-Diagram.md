---
title: Block Diagram, Protocol, and Message Structure
---

## 1. Team Block Diagram 

Below is a Block Diagram built of our project. In this figure we will show how we intend to connect our individual subsystems to build our project. We plan on mainly communicating through UART. However our HMI and Controller systems do also have a wireless communication protocol.





## 2. Sequence Diagram of Team Communication

This diagram will demonstrate how our communication will travel through our system for each message type.

Motor set parameter and print value:
``` mermaid
sequenceDiagram
    autonumber
    actor User
    participant HMI
    User->>+SamB: Hello I'd like to move forward.
    SamB->>+Adrian:Move forward.
    Adrian->>+Andrew: Motors start forward.
    Andrew->>+Jacob: Motors start forward.
    Jacob->>+SamM: Motors started forward.
    SamM->>+Mo: Motors started forward.
    Mo->>+Adrian: Motors started forward.
    loop while user wants to go forward
        Adrian->>+Andrew: Get forward speed.
        Andrew->>+Jacob: Print forward speed value.
        Jacob->>+SamM:Print forward speed value.
        SamM->>+Mo: Print forward speed value.
        Mo->>+Adrian:Print forward speed value.
        Adrian->>SamB: Motors going forward at ___ speed.
        SamB->>User: Moving forward at this speed.
    end
```

Return a sensor value:
``` mermaid
sequenceDiagram
    autonumber
    actor User
    participant HMI
    User->>+SamB: Hello I'd like to know the temperature.
    SamB->>+Adrian: Get temperature.
    Adrian->>+Andrew: Get temperature.
    Andrew->>+Jacob: Get temperature.
    Jacob->>SamM: Get temperature.
    SamM->>Mo: Here's the temperature.
    Mo->>Adrian: Here's the temperature.
    Adrian->>+SamB: Here's the temperature value.
    SamB->>+User: Here's the temperature requested.
```

TEST <!-- remove this example -->
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