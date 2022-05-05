# Assignment SE 211

## The "gateway" to our masterpiece:


<p align="center">
    <img src="https://user-images.githubusercontent.com/75155228/141804519-cc87e741-c06a-41cd-950f-88a2bd930dd5.png">
    <br> Accessible through a website too: https://ktvtpos.netlify.app/</br>
</p>

[![hackmd-github-sync-badge](https://hackmd.io/sE5viRzKQe6kvRmY17ShIw/badge)](https://hackmd.io/sE5viRzKQe6kvRmY17ShIw)

## Timeline
- Start
- Meeting first time: 31/08/2021
    - [x] Read Assignment Description
    - [x] Github practise
    - [x] Choose technology in case writing code Svelte
- Task 1:
    - Next meeting day: 07/09/2021
    - [x] Do task 1 draft complete version
    - Next meeting day: 14/09/2021
    - [x] Review work of task 1
    - Next meeting day: 21/09/2021
    - [x] Prepare for final version
- Task 2
    - Next meeting day: 21/09/2021
    - [x] Assign job on task 2
        - KPI 50%: 28/09/2021
        - KPI 100%: 02/10/2021 20h
- Task 3
    - First meeting day: 04/10/2021
    - [x] Assign job on task 3
    - [x] Completing task 2
- Task 4
    - First meeting day: 04/10/2021
    - [x] Assign job on task 4
    - Second meeting day: 12/10/2021
    - [x] Improve task 2
    - Third meeting day: 19/10/2021
    - [x] Improve task 3
    - Fourth meeting day: 26/10/2021
    - [x] Report task 4 achievement
- Task 5
    - First meeting day: 26/10/2021
    - [ ] Assign job on task 5
- End

## Role
### Task 1:
**GG Docs for link in txt file -> build PDF to put on Github**
- Tam: Context of project + stakeholder
- Khoi: Expect + Scope
- Viet: Task 1.2 (func + non-func Ctrl+C+V) + redraw diagram
- Thanh: Task 1.3 (use Khoi diagram to fix Viet table)
- Task 1.1:
    - Context of project: combine of @Tam (base on PDF)
        - Thanh & Viet version: Detail on how manager contact of application
        - Khoi: make up based on reality
    
        => **Thanh + Viet**
        
    - Stakeholders:
        - Khoi: Customer, Manager, Chef
        - Viet: Customer, Manager, Chef, IT staff (maintain), Bank (payment), Cashier
        - Tam: Add waiter & waitress (special recommendation), regulator ( (merge manager + IT staff)
        - **Add? supplier**
        
        => **Viet + Tam**
        
    - Expectation to be done:
        - Khoi + Viet + Thanh: Detail how system works
        - Tam: Responsive web base POS system
        
        => **Khoi + Thanh + Viet => summary: Tam**
        
    - Scope of the project
        - Khoi: involvement and non-involement of system
        - Tam + Viet + Thanh: applied to one restaurant => future expand

        => **Tam + Viet + Thanh**
        
- Task 1.2:
    - Func requirement:
        - Customer can scan the QR code to go to the restaurant’s website.
        - Customer can select a meal from a menu list and then order.
        - Customer can give feedback in the website after ordering the food.
        - The clerk can check and confirm all the orders from customers.
        - When the order is unavailable, the system can send a notification to the clerk.
        - When the order is available, the system could handle the payment by using credit card of the customers and record it.
        - The cook can see all the valid orders from the system.

    - Non-func requirement:
        - The system should allow non-direct contact between Clerks and Customers
        - The system should be implemented using Web technology and QR code, so customers will not have to install apps
        - The system should be usable from a mobile device, a tablet device or a normal computer/laptop
        - The system should be extendable to use in multiple restaurants in the future
        - The current transactions is about 300 orders per day.

    - Use-case diagram for whole system
        - Thanh: change "check out" -> "order food"
            - Credit card + cash is "extend"
            - Remove "reorder"
            - Change "login, logout" into "access the system" **tmp**
            - Admin: "Manage food" -> "Manage menu"
            - Admin: "Manage order" -> "View order record"
        - **Viet**: redraw diagram based on features of Thanh + Viet
- Task 1.3:
    - Use-case diagram: Use Khoi + new feature (ask other team + teacher)
    - Table format: Viet's work (will changed to add new features)

Changelog on meeting 14/09/2021:
- Diagram from task 1.3 -> 1.2
- Remove "cash" => payment -> pay by credit card
- Access the system -> access the menu

#### New task arrives
- Viet: Fix the picture of task 1.3 -> convert to become 1.2 task (**DONE**)
- Viet: Choose feature from task 1.2 to become 1.3 (**DONE**)
- Thanh: Choose corresponding table format for task 1.3
- Tam: Check tables
- Tam: Check on other teams' works
- Khoi: Merge all the works in task 1 to LaTEX report
- Whole team: Research Sequence Diagram

### Task 2:
- KPI 50%: 28/09/2021
- KPI 100%: 02/10/2021 20h
- Activity diagram @DuckyHCMUT
    - [60 minutes free trial version](https://drive.google.com/file/d/1z4Apbj6JEdr8gQ-nurVvgW2QjEbWoXiY/view?usp=sharing)
    - [Description](https://drive.google.com/file/d/1ayZZVkret1VaGIOJHNOy5jAALYxYf2uW/view?usp=sharing)
    - [Final version for description](https://docs.google.com/document/d/1QvJ-FNeYZwGCJ3KXAoEOVmg0UyLO9QTi8TDpUUo0_js/edit?usp=sharing)
- Sequence diagram @Thanh
    - [Draft version](https://drive.google.com/file/d/1kUHWp0KpL8a2EbSyKWWiS0QQ-7jZfa8r/view?usp=sharing)
    - [Description](https://drive.google.com/file/d/1MstMpxWvCkFkw9ryHpZduMk5NBG2dCog/view?usp=sharing)
- Class diagram @tokisakikurumi2001
    - [Draft version](https://drive.google.com/file/d/1rFQdTpJe3hNUpcP6JfSJGpoBdsSyHScx/view?usp=sharing)
    - [Description](https://docs.google.com/document/d/1BKb8b3qqRNSxSIJ3DBopDwEbqjqW3TpNioRBfScpNGA/edit?usp=sharing)
- Tam: check LaTex file and checkout other group

**NOTE**:
- [x] 2.3 relevant stakeholder -> remove shipper

### Task 3:
- KPI 100%: **21h 15/10/2021**
- Approach: @Khoi, @Thanh
    - Choose MVC
    - Flow:
        - Introduction to MVC (Tam)
            - [Description](https://hackmd.io/@pzPdS5TbSTqOR0nPsZHGVg/r1LNeiFHY)
        - Adv of MVC (Thanh)
        - Dis of MVC (Thanh)
        - Mapping MVC into our system, with diagram (like in the slide) (Khoi)
            - [Diagram](https://drive.google.com/file/d/1BC5g4ubjBDoyijmxoPFv-IuaOKK5DEoa/view?usp=sharing)
            - [Description](https://docs.google.com/document/d/1UfuL9UkT9IJn-YlHDm4-3VP13HQNV3KJfGgpmHCy7gw/edit?usp=sharing)
- Implementation diagram: @Tam, @Viet
    - [Draft version from Tam](https://drive.google.com/file/d/1RikNMm0KxmqdCUdHRWNgHhbQozUdFMu_/view?usp=sharing)
    - [Description from Tam](https://hackmd.io/@pzPdS5TbSTqOR0nPsZHGVg/SyxILCGSY)
    - [Draft version from Viet (Component + Deployment + Package diagram)](https://drive.google.com/file/d/1q3YUJW0pP102p4OOO9ggyAMlAFpcj-G3/view?usp=sharing)
    - [Description from Viet](https://docs.google.com/document/d/1EYfdlmvPPD9OzgJBtrgP_iZNVM1FM-p9vVTulgNzSo0/edit?usp=sharing)

### Task 4:
![](https://i.imgur.com/895xRGQ.png)

### Task 5:

## Problems during execution
### Get the answer
- Context of project vs context model (Chapter 5 section 1)
    - Context of project is jus a common situation (we are heading the right way)
    - Context model -> use for different kind of diagram studied later in chapter 5
- What is the dashed line inside workflow diagram?
    - ----> (full line arrow): sequence of action, action happened right after another action
        - The customer order the meal, the clerk need to immediately confirm the order
    - \- \- \-> (dashed arrow): the action will happen, but **NOT** neccessarily immediate
        - For example, customer need to pay the order, but not right after placing order. Can pay after receiving the meal.
- What exactly is MVP? 
    - In the assignment, we need to make UI interface, including
        - Show the menu as shown in figure 2
        - When hitting the button icon `cart`, show the details description of meal as shown in figure 3
        - When user hit the button payment, create hyperlink to show payment screen (as shown in figure 4)
- What technology to implement MVP?
    - Right now, [Svelte](https://svelte.dev) is a good choice

### Did not get the answer
- What does table format of use-case diagram?
- In the task 1.2 diagram, `manage order` should extend by add food or delete food || `manage order` become CRUD example

## Reference
### Task 1
Chapter 4 in the book

[Use case diagram](https://thinhnotes.com/chuyen-nghe-ba/use-case-diagram-va-5-sai-lam-thuong-gap/)

### Task 2
Chapter 5 in the book

### Task 3
Chapter 6 in the book

### Task 4

[Github](https://github.com/Dunebook/SvelteEcommercecart)

### Task 5
