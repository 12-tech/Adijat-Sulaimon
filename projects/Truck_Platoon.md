---
layout: project
type: project
image: img/Truck_Platoon/Block Diagram.jpg
title: "Truck Platoon System"
date: 2025
published: true
labels:
  - Rtos
  - C++
  - TCP/IP
  - RMS Scheduling
  - Server-Client Architecture
  - SysML
summary: "My team developed a truck platoon system for autonomous vehicle coordination, focusing on real-time platoon reconfiguration and performance optimization."

---

<div class="text-center p-4">
  <img width="200px" src="..img/Truck_Platoon/Screenshot 2025-02-04 at 23.45.15.png" class="img-thumbnail" >
  <img width="200px" src="..img/Truck_Platoon/internal block diagram.jpg" >
  <img width="200px" src="../img/micromouse/micromouse-circuit.png" class="img-thumbnail" >
</div>

For this project, my team and I developed a truck platoon system aimed at improving autonomous vehicle coordination for modern logistics. The system used a distributed and parallel architecture, with a server-client model over TCP/IP to ensure reliable and efficient communication between the platoon vehicles, including leader trucks, follower trucks, and external vehicles such as cars. A key aspect of the project was enabling the platoon to dynamically adjust its formation when an external vehicle tried to pass between the trucks. This real-time platoon reconfiguration was managed through a robust communication protocol, which exchanged vital data regarding speed, distance, and formation changes.

I was specifically responsible for designing and implementing the communication protocols (V2X and V2P) to ensure effective message-passing between platoon members and external vehicles. Additionally, I contributed to the system’s architecture, which was designed using SysML and UML, allowing for clear representation and understanding of component interactions. We also employed GPU computation to handle logical matrices for optimized performance and quick decision-making in real time. For scheduling and task management, I worked on implementing the Rate Monotonic Scheduling (RMS) algorithm, ensuring that tasks were prioritized based on their frequency. Additionally, I contributed to the verification and validation of the system, with an initial focus on testing the serialization and deserialization of message objects.

We simulated the system using Tinkercad, which allowed us to observe and refine the platoon’s behavior in dynamic traffic scenarios. The system was developed in C++, ensuring computational efficiency to meet the real-time processing requirements. The results showed the system’s ability to adapt to the environment in real time and maintain platoon stability, making it a viable solution for autonomous fleet management.

Here is some code that illustrates how we read values from the line sensors:

```cpp
byte ADCRead(byte ch)
{
    word value;
    ADC1SC1 = ch;
    while (ADC1SC1_COCO != 1)
    {   // wait until ADC conversion is completed   
    }
    return ADC1RL;  // lower 8-bit value out of 10-bit data from the ADC
}
```

You can learn more at the [UH Micromouse News Announcement](https://manoa.hawaii.edu/news/article.php?aId=2857).
