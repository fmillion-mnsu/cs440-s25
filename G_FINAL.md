# Group Capstone Project

This project serves as the capstone and the "Final" for CS 440. 

For this project, you will work in your group to decide upon and *implement* a data model for a data-driven project. You will consider an application or data-focused project scenario, build a data model that involes multiple types of database servers, and **implement** the data-access layer of that model using a programming language of your choice.

If your group agrees, you **may** use one of your group members' CS projects as the subject of your data modeling project provided the project is not NDA. However, even if your project does not require all of the aspects given in these requirements, you still need to include those aspects. This might mean "thinking outside the scope" of your current project and considering how additional database types might apply to your project in a future iteration.

## Requirements

1. Your group should consider an application, data management scenario, or similar project that would involve a fairly large number of data entities and paradigms. 

    If you are completely stuck and can't think of any good ideas, here's a few that you can use as a foundation for your project (but please **expand** upon these with specifics!):

    * A commercial music or video streaming service. Consider entities like users, subscription tiers, recommendations...
    * A course management system for a university. You can use your knowledge of MSU if you like. Consider entities such as students/faculty, course prerequisites, grades...
    * A retail store management system. Consider entities such as customers, products, orders/sales, inventory, suppliers...

2. Design and document the data management strategy for your project. 

    For some data elements, you will want to use relational databases. However, you will also need to consider how the following types of databases will fit into your project:

    * Document-based databases
    * Graph databases
    * Memory cache databases
    * Time-series databases
    * Blockchain databases
  
    **Your project must include at least THREE (3) types of databases**, including relational databases. For example, a data model that uses relational, document and time-series databases would be sufficient.

3. **Implement** your data model on actual database servers.

    To achieve this step, you have two options. You can either download and run the database engines yourself using Docker, or you can ask me to provide you with cloud servers. Since you will need to run three separate database engines, less-powerful machines may struggle with this task; if you have any trouble or simply don't want to bother with doing all the setup yourself, please reach out to me by Email with your request for servers and I will provide you with access ASAP.

    > [Click here to go to the reference document illustrating how to setup Docker and install and use all of the databases we have discussed in class.](DBSETUP.md)

4. Using a programming language of your choice, **design and write at least six (6) functions/methods that implement typical operations you will need to do on your data model**. You should "touch" all types of databases you include in your queries. For example, it would not be sufficient to design a model with relational, document and graph databases, but only write querires against the relational database portion or only the relational and graph portion. Prioritize operations that cross between the databases if you need to!

5. Design a short PowerPoint presentation (no more than 10 minutes total) illustrating your data model and demonstrating your implementation. 

    You will present your final presentation on the last day of this course (May 1, 2025).

    You will also submit your code, data design document/models, and your PowerPoint presentation to D2L no later than **Friday, May 9** at **11:59 PM**.

