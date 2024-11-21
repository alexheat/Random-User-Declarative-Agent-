# Random-User-Declarative-Agent- (Unofficial Sample App)
Sample Declarative Agent for Microsoft 365 Copilot using the public random user generator API at https://randomuser.me/. This tutorial uses the Teams Toolkit and Visual Studio Code to build the sample agent, if you have not used the Teams Toolkit before I recomend completing this official tutorial first [Create declarative agents using Teams Toolkit](https://learn.microsoft.com/en-us/microsoft-365-copilot/extensibility/build-declarative-agents?tabs=ttk).

## Planning the Agent
I am a member of the Microsoft Copilot team working on the Declarative Agent platform and I created this sample app to explore and test building an agent that retrieves data from external APIs (also known as actions). 

My first step was finding a suitable API. At [Apipheny](https://apipheny.io/free-api/), a site offering a collection of free public APIs, I discovered a random user data generator [randomuser.me](https://randomuser.me)). This open-source API provides details about a fictional user, including gender, name, email, and address—a “Lorem Ipsum” for user data.


## Build the Open API Specification File
The creators of Random User don’t provide an OpenAPI specification file, but you can use Copilot to generate one from the available documentation. Try this prompt:

```
Can you create an open API specification from this web page https://randomuser.me/documentation
```

![image](https://github.com/user-attachments/assets/35db6f72-e40b-42c5-9300-885100e9fa94)

Next ask Copilot to save it as a YAML file
![image](https://github.com/user-attachments/assets/74d85d5d-83db-4c15-b442-b4e91775cd4a)

## Build the Declaritive Agent Using the Teams Toolkit and Visual Studio Code
In the Teams Toolkit, select **Create New App**, select Agent, Declarative Agent, Add Pluging, and then select “Start with an OpenAPI Description Document”, and browse to to the YAML file. 
![alt text](image.png)
The Teams Toolkit will build the files needed for a declaritive agent, the files you want to edit to add the functionality are in the /[appPackage](https://github.com/alexheat/Random-User-Declarative-Agent-/tree/main/Random%20User/appPackage) directory.

![image](https://github.com/user-attachments/assets/c4aa467d-a1e9-4925-b401-e886baf230ae)
The only 2 files you probably to modify are instructions.txt (where you put the LLM instructions for what the agent should do) and declarativeAgent.json (where you can add the conversation starters) and add additional capabilites like Web or SharePoint search. 

When you're ready, select Provision to validate the agent, package it into a .[zip](https://github.com/alexheat/Random-User-Declarative-Agent-/blob/main/Random%20User/appPackage/build/RandomUser.zip) file, and load it into Copilot so you can use it. 


