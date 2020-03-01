# Branching Policies

“I am [Marc Rosell](https://www.linkedin.com/in/marc-rosell-hernandez-a19188150/), student of the [Bachelor’s Degree in Video Games by UPC at CITM](https://www.citm.upc.edu/ing/estudis/graus-videojocs/). This content is generated for the second year’s subject Project 2, under supervision of lecturer [Marc Garrigó](https://www.linkedin.com/in/mgarrigo/).”

## Concept

Branching methods in projects help teams to work in parallel and to solve any problem or implement features in a simpler way, so that, there are policies to maintain control over all of them.
Branching Policies are a set of rules created to help teams protect their branches of development. These policies enforce team's code quality and management. 

To see the benefits of using Branching Policies, we will take a deeper look to two different ways of working with branches. The first one being a light branch policy and the second one with a much more strict policies, that is used by companies.

### Trunk-Based Development
On one hand, the Trunk-Based Development is very similar to the one used in previous subjects, but using 2 branches. One branch is where the entire team **works in the development** of the features and separately has the branch for **releases**. Using this structure, when someone checks-in with wrong code it must be fixed in order to continue working (the entire team must wait for a fix). Now a days, this policy is outdated by the **Feature Branching Development**.

There are two types of Trunk-Based Development:
* **Trunk-Based Development for Smaller Teams:**
![trunk-dev](https://trunkbaseddevelopment.com/trunk1b.png)

In this method, there are usually a small amout of programmers, each one **commiting straight into the trunk** or master. All the implementations must pass a pre-integration step, **running the build first**.

* **Scaled Trunk-Based Development:**
![scaled-trunk-dev](https://trunkbaseddevelopment.com/trunk1c.png)

This method is best done with **short-lived feature branches**, for example: one person working for a maximum of two days. Then should pass a **Pull-Request style code-review**, before merging into the trunk.


### Feature Branching Development
On the other hand there is the Feature Branching Development, in which all the features and implementations are made **external to the main branch** and only integrated when they are completed, so the problem of waiting for the errors to be solved on the Trunk-Based Development is unexistant. In spite there are **other inconceniences**. For example, as the feature branches are used for a larger amout of time, if it isn't up to date, it could end up giving problems when merging with the main branch.

**Git Flow** is a branch policy for the Feature Branching Development:


## Explain very clearly the use for each case


## How to structure QA around gitflow ?


## Homework 
* Create a Github Project and put to test.
* Think and create the barnching system for your project repository.

## Sources
[A Successful Git Branching Model](https://nvie.com/posts/a-successful-git-branching-model/)

[Administrating a Repository - Protected Branches](https://help.github.com/en/github/administering-a-repository/about-protected-branches)

[AppVeyor](https://www.appveyor.com/docs/branches/)

[Atlassian Bitbucket](https://www.atlassian.com/git/tutorials/comparing-workflows)

[Azure Branching Policies](https://docs.microsoft.com/en-us/azure/devops/repos/git/branch-policies?view=azure-devops)

[Azure Pull Requests](https://docs.microsoft.com/en-us/azure/devops/repos/git/pull-requests?view=azure-devops&tabs=new-nav#complete-the-pull-request)

[Collaborating with Issues and Pull Requests](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests)

[DevOpsNet](https://devopsnet.com/2012/11/01/exciting-branching/)

[Git Branching Workflow](https://git-scm.com/book/en/v2/Git-Branching-Branching-Workflows)

[IT Hare](http://ithare.com/version-control-branching-for-gamedev/)

[Trunk-Based Development](https://trunkbaseddevelopment.com/)
