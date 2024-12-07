# Constraints formulated as maths equations

- Our university has:
    - A given **r** number of rooms. Each room might be a **special room**.
        - **Special rooms** are rooms with specific furnitures. For instance lab furnitures are in **lab** rooms. **Lab** rooms are considered as a **special room**.
        - Rooms that aren't **special rooms** are refered too as **rooms**.
        - **Amphitheatres** are considered as **special rooms**.

        - Let $r$ be the number of rooms, $r_{special}$ the number of special rooms. We must ensure that:

            $$r\in\mathbb{N} \\  r_{special} \le r$$

    - A given **t** amount of teachers. Each teacher has one or more corresponding subjects he/she can teach.
        - Let $t$ be the number of teachers.

        $$t \in \mathbb{N}$$ 

    - **N** promotions (= year the student is on).
        - Let $N_{promotions}$ be the number of promotions: 
        
            $$N_{promotions} \in \mathbb{N}$$

    - Each promotion has:
        - **n** classes (= group of students).
            - Let $n_{classes}$ be the number of classes: 
            
            $$n_{classes} \in \mathbb{N}$$
            
        - To each class, we assign **s** subjects (= materials) the class has to attend.
            - Let $s$ be the number of subjects. 
                    
            $$s \in \mathbb{N}$$
              
- Each of the **s** subjects has:
    - A fixed number of hours **h** to be completed.

        - Let $h_s$ the number of hours that must be completed as part of this course and $h_{s_a}$ the currently attributed hours for this subject.

        - Let $t_{s_i} , \forall i \in \mathbb{N}$ be a timeslot attributed to subject $s$. $h_{s_a}$ is defined as:

            $$h_{s_a} = \sum_{i=0}^{h_s} t_{s_i}$$
        
        - We must ensure:
            $$h_{s_a} = h_s$$

    - The **h** hours are divided in **online_hours** and **presential_hours**.
    - We need to make sure that **online_hours** <= (30%) * **h**

        - Let $h_{s_o}$ the number of online hours attributed to subject $s$ and $h_{s_p}$ the number of presential hours attributed to subject $s$. We must ensure:

            $$h_{s_a} = h_{s_p}+h_{s_o} \\ h_{s_o} \le 0.30\times h_{s_a}$$
      
- To complete the **h** hours:
    - One course duration is 1h30.
        - Let $t_i$ be an assignated timeslot. We must ensure that:

        $$\frac{\sum_{i=0} t_i}{1.5} = k , k\in\mathbb{N}$$


    - A class can attend as many **courses** as required to attend the **h** hours.

        - Reminder : $h_s$ is the number of hours that must be completed as part of a course. Thus:

        $$h_s \in \mathbb{R}^+$$

    - Some **courses** need to take place in special rooms depending on the **course**'s format. (For example practical works need to be in labs)
    - Two different classes can't attend the same **course** in the same **room** on the same **timeslot**
        - An exception is made for **courses** taking place in **amphitheatres**
    - One class can't have two **courses** in the same **timeslot**
      
- The **courses** can take place in defined **timeslots** each day.
    - **Timeslots** are defined as follows:
        - 08:15 to 09:45
        - 10:00 to 11:30
        - 11:45 to 13:15
        - 13:30 to 15:00
        - 15:15 to 16:45
        - 17:00 to 18:30
        - 18:45 to 20:15
    - No **course** can be scheduled on saturday and thursday afternoon (from 13:30 to 20:15). No **course** ca be scheduled on Sunday.
    - Students must have at least one free slot a day. Either 11:45 to 13:15 or 13:30 to 15:00. This is to ensure they can eat.
    - **Courses** can be either **online** or **presential**. Respecting the previous condition regarding total amount of online hours.
    - Certain **courses** may require specific time slots due to logisitcal reasons. (e.g. lab courses requiring 3h sessions, thus, two back-to-back **timeslots**)
      
- To take place, each **course** needs:
    - An available room. (= A room where there is no course taking place)
    - A corresponding **class**
    - A **teacher** that can teach the **course**'s subject.
        - The **teacher** must be available. He can't give two courses at the same time.
        - The **teacher** may have preferred teaching time or days. The **schedule** should try to accomodate these perferences as much as possible.

- Room and Resource Allocation:
    - Scheduling must allocate regular or special rooms (e.g., labs or amphitheaters) based on course requirements.
    - Ensure adequate use of room resources while preventing overbooking or misuse of special-purpose spaces.