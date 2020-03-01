# Branching Policies

“I am [Marc Rosell](https://www.linkedin.com/in/marc-rosell-hernandez-a19188150/), student of the [Bachelor’s Degree in Video Games by UPC at CITM](https://www.citm.upc.edu/ing/estudis/graus-videojocs/). This content is generated for the second year’s subject Project 2, under supervision of lecturer [Marc Garrigó](https://www.linkedin.com/in/mgarrigo/).”

## Concept

Branching methods in projects help teams to work in parallel and to solve any problem or implement features in a simpler way, so that, there are policies **to maintain control** over all of them.
Branching Policies are a set of rules created to help teams protect their branches of development. These policies enforce team's code quality and management. 

![branches](https://github.com/MarcRosellH/BranchingPolicies/blob/master/docs/baixa.png?raw=true)

To see the benefits of using Branching Policies, we will take a deeper look to two different ways of working with branches. The first one being a light branch policy, the **Trunk-Based Development**, and the second one with a much more strict policies, that is used by companies, the **Feature Branching Development**.

## Trunk-Based Development
On one hand, the Trunk-Based Development is very similar to the one used in previous subjects, but using 2 branches. One branch is where the entire team **works in the development** of the features and separately has the branch for **releases**. Using this structure, when someone checks-in with wrong code it must be fixed in order to continue working (the entire team must wait for a fix). Now a days, this policy is outdated by the **Feature Branching Development**.

There are two types of Trunk-Based Development:
### Trunk-Based Development for Smaller Teams:
![trunk-dev](https://github.com/MarcRosellH/BranchingPolicies/blob/master/docs/trunk.png?raw=true)

In this method, there are usually a small amout of programmers, each one **commiting straight into the trunk** or master. All the implementations must pass a pre-integration step, **running the build first**.

### Scaled Trunk-Based Development:
![scaled-trunk-dev](https://github.com/MarcRosellH/BranchingPolicies/blob/master/docs/scaled-trunk.png?raw=true)

This method is best done with **short-lived feature branches**, for example: one person working for a maximum of two days. Then should pass a **Pull-Request style code-review**, before merging into the trunk.


## Feature Branching Development
On the other hand there is the Feature Branching Development, in which all the features and implementations are made **external to the main branch** and only integrated when they are completed, so the problem of waiting for the errors to be solved on the Trunk-Based Development is unexistant. In spite there are **other inconceniences**. For example, as the feature branches are used for a larger amout of time, if it isn't up to date, it could end up giving problems when merging with the main branch.

**Git Flow** is a branch policy for the Feature Branching Development:
![gitflow](https://github.com/MarcRosellH/BranchingPolicies/blob/master/docs/gitflow.png?raw=true)

This policy arises from the needs of organising a team of people to work in a same project and standards that may not have clear instructions on how to act in every situation that may come up, making it almost impossibl to work. So that, this set of rules, **protect the main branches**, making the administrator the only who can manipulate it, preventing possible repository damages.
The memebers of the team can pull request and merge the branches on which they work (feature to develop), but in terms of **develop, release, hotfixes and master branches** the administrator is the only one who with permission to allow modifications to the main branches. Therefore, there might be more than one administrator. A nice method would be:

* Lead Programmer managing develop and hotfixes branches.
* QA Lead managing releases and master branches.

This will lead to a better QA testing using the Git Flow policies.

The other memebers of the team interact with these main branches by **branching off from develop** and creating their feature branch, in which they implement it and, after passing all needed verifications, **merge it back** to the develop branch creating a pull request.

The **QA testing** is done in the **release branch** if it's a low grade bug, fixing it in this same branch and then merging back the branch into the develop branch. If is a high grade bug then it would imply the creation of a **hotfix branch**.

### Extra Rules
![rules](https://github.com/MarcRosellH/BranchingPolicies/blob/master/docs/policies-config.PNG?raw=true)

Github, when the branches have been created, allows to **add rules** to the branches, for a better working of it and the team. For example, the verification that has to pass to complete a pull request, mentioned earlier.

To add these rules go to your repository then: **Settings>Branches>Add Rule**

## Git Flow Structure In Detail
The generic structure is:
![gitflow-structure](https://github.com/MarcRosellH/BranchingPolicies/blob/master/docs/gitflow-structure.png?raw=true)

We can distiguish the next branches:
### Master and Develop Branches
In the Git Flow structure, these two branches are parallel and infinite, since their creation at the beginning of the project until its end. The master branch is **only updated with the main stable versions** of the project.
![develop-and-master](https://github.com/MarcRosellH/BranchingPolicies/blob/master/docs/master-develop.png?raw=true)

### Feature Branches
The feature branches are where the developers work on their own respective fields and tasks to develop different parts of the release in which the whole team is working. It is needed for these branches to **keep updated** with all the progress done in the develop branch, to avoid problems while merging.

![feature](https://github.com/MarcRosellH/BranchingPolicies/blob/master/docs/feature.png?raw=true)

* Branch off from:
**develop branch**
* Merge back into:
**develop branch**

### Release Branch
Since all the features developed are in the develop branch, the release branch will serve as a support branch for the upcoming release. In this branch is where the **QA testing** is done. The issues are reported and **are solved in this same branch**. When the bugs are fixed, it is needed to **merge back to the develop branch**. Once it's all tested, almost everything fixed and confirmed to release, the metadata of the project as the version, is prepared. Then the branch merges with the master branch for the release launch into the master branch.

![release](https://github.com/MarcRosellH/BranchingPolicies/blob/master/docs/release.png?raw=true)

* Branch off from:
**develop branch**
* Merge back into:
**develop and master branches**

### Hotfix Branch
Hotfix branches are like release branches, to prepare a new release,yet unplanned. Is is created when a **critical bug in a production release** has been detected and must be immediately solved. One member can work on the problem while the rest keep working on their feature branches. Once the bug is solved, the tag must be changed, and it must merge into master and develop branches.

![hotfix](https://github.com/MarcRosellH/BranchingPolicies/blob/master/docs/hotfix.png?raw=true)

* Branch off from:
**master branch**
* Merge back into:
**develop and master branches**

## AppVeyor, Jenkins, Travis CI & others
Applications like **AppVeyor, Travis CI, Jenkins, GitLab** and others are made to help in the QA process. When connected with Github, their servers generate a build version of the project (need to be adjusted by the user).
If it is configured to create the builds only when the commits are made in the **release, master and hotfix branches**, the QA testers don't need to do it by themselves and can start directly to test it.

![jenkins](https://github.com/MarcRosellH/BranchingPolicies/blob/master/docs/jenkins.png?raw=true)

## Homework 
* In groups, structure your project using the Git Flow structure.

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

[Jenkins](https://jenkins.io/doc/)

[Travis CI](https://docs.travis-ci.com/)

[Trunk-Based Development](https://trunkbaseddevelopment.com/)
