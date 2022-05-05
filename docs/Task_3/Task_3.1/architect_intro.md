# Introduction to MVC

Before applying the MVC to our system, we would like to introduce some key features of the MVC and its pros and cons.

## 1. What is MVC?

MVC stands for Model View Controller. It is a design pattern which separates presentation and interaction from the system data. The system is structured into three logical components that interact with each other.

- The Model component manages the system data and associated operations on that data.
- The View component defines and manages how the data is presented to the user.
- The Controller component manages user interaction and passes these interactions to the View and the Model.

## 2. When to use MVC?

MVC is used when there are multiple ways to view and interact with data. It is more of an architectural pattern, but not for a complete application. It is also used when the future requirements for interaction and presentation of data are unknown. MVC mostly relates to the UI/interaction layer of an application.

## 3. Advantages

In here we introduce some advantages of MVC that we think it is suitable for our system:

- Easily modifiable: Using the MVC methodology allows easy modification of the entire application. It allows the data to change independently of its representation and vice versa. So, any changes in a certain section of the application will never affect the entire architecture. This, in turn, will help to increase the flexibility and scalability of the application.
- Multiple views: In the MVC architecture, developing different view components for your model component is easily achievable. It supports presentation of the same data in different ways, with changes made in one representation shown in all of them.
- Easy planning and maintenance: The MVC paradigm is helpful during the initial planning phase of the application because it gives the developer an outline of how to arrange their ideas into actual code. It also helps limit code duplication and allows easy maintenance of the application.

## 4. Disadvantages

Besides the advantages, MVC pattern also has some disadvantages that we want to illustrate:

- High complexity: The MVC pattern introduces new levels of indirection and this increases the complexity of the solution. In some cases, it is not right suitable for small applications which has adverse effect in the application's performance and design.
- Cost of frequent updates: developers cannot completely ignore the view of the model even if they are coupled. If the model undergoes frequent changes, the views could be flooded with update requests.
