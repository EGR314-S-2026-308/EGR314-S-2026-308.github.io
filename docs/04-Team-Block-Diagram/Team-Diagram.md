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

Subsystem Status Check Code/Message:

``` mermaid
sequenceDiagram
    autonumber
    actor User
    participant HMI
    participant SamB
    participant Adrian
    participant Andrew
    participant Jacob
    participant Sam
    participant SamM
    participant Mo

    User->>SamB: Request Status Check
    SamB->>Adrian: Initiate Status Check

    Adrian->>Andrew: Status [Adrian: OK]
    Andrew->>Jacob: Status [Adrian: OK, Andrew: OK]
    Jacob->>Sam: Status [Adrian: OK, Andrew: OK, Jacob: OK]
    Sam->>SamM: Status [Adrian: OK, Andrew: OK, Jacob: OK, Sam: OK]

    SamM->>Mo: Status [Adrian: OK, Andrew: OK, Jacob: OK, Sam: OK, SamM: N_OK]
    Mo->>Adrian: Forward [Adrian: OK, Andrew: OK, Jacob: OK, Sam: OK, SamM: N_OK]

    Adrian->>SamB: Alert [SamM: N_OK]
    SamB->>User: Temperature Sensor Failure

    loop Until SamM OK
        Adrian->>Andrew: Recheck Status
        Andrew->>Jacob: Forward Check
        Jacob->>Sam: Forward Check
        Sam->>SamM: Recheck Status
        SamM->>Mo: Status [SamM: NOT OK]
        Mo->>Adrian: Forward [SamM: NOT OK]
        Adrian->>SamB: Rechecking
        SamB->>User: System Not Ready
    end

    SamM->>Mo: Status [SamM: OK]
    Mo->>Adrian: Forward [SamM: OK]
    Adrian->>SamB: [SamM: OK]
    SamB->>User: System Ready
```

Subsystem Error Code/Message:

``` mermaid
sequenceDiagram
    autonumber
    actor User
    participant HMI
    participant SamB as Sam B 
    participant Adrian as Adrian 
    participant Andrew as Andrew
    participant Jacob as Jacob 
    participant Sam as Sam 
    participant Mo as Mo 

    Note over Jacob: Motor error!
    Jacob->>Sam: Error 0x01 (Motor Stall)
    Sam->>Mo: Error 0x01
    Mo->>Adrian: Error 0x01
    Adrian->>Andrew: Error 0x01
    Andrew->>SamB: Error 0x01
    
    SamB->>User: Shows "MOTOR ERROR"
    

    
    loop while error active
        Adrian->>Andrew: Status check
        Andrew->>Jacob: Status check
        Jacob->>Sam: Motor still bad
        Sam->>Mo: Motor still bad
        Mo->>Adrian: Motor still bad
        Adrian->>SamB: Motor not recovered
        SamB->>User: "Shows Motor Error"
    end
    
    Jacob->>Sam: Motor OK now
    Sam->>Mo: Motor OK now
    Mo->>Adrian: Motor OK now
    Adrian->>Andrew: Motor OK now
    Andrew->>SamB: Motor OK now
    
    SamB->>User: "System ready"
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



Message Type 67:

| **Byte 1-2(uint16_t)** | **Byte 3 (uint8_t)** |
| :--------------------: | :------------------: |
| 0x43                   | Button # (uint8_t)   |

The rest of the Bytes can be a string containing a message or empty space.
