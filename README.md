# domino_base
Three Actors in the Methodolgy GitLab Migration

Methodology,  Model Valudation MRMC,  Model IT (Vertical), RiksLab Model Service IT (Horizontal) 

Methodology GitLab roles: 
Builder Manager
Developer
Guest


Methodology Requirements
On Code Development: 
1) Model code is currently co-developed by Methodlogy and IT in IT Gitlab Repo, Methodology strategic vision is in future Mehtodology should indepdently produce Production ready code.
2) Model code is owned by methodology only, meaning ONLY the methodology can merge branches / forks to main branch. IT is not allowed to perfrom merge. but can partipate in a Pod to make changes in a branch or fork. 
On Git accesses:
1) IT ideally should only be given Guest Read Only access, allowing them to fork out to IT repo / personal repo for development. 
2) If forking is not an option, Developer access can be granted with the condition IT will never be set as merge approver nor trigger off production built CICD Pipelines. 
3) MRMC shall not have any access to Methodology GitLab.
On CICD Build: 
1) Only model methodolgy can trigger the production artifect build process. 
1) Some methodology prefers to own CICD configuration if RiskLab Model Service IT could simplifies /standardise and template the configration and automation process. 
2) Some methodology for Model IT team to take over the entire CICD process. 
On MRMC Sumbission. 
1) Only a copy of the GitLab code, (i.e. no Git history) can be sumbitted to MRMC. For sumbitting new version, a new code copy is made.
2) Some methodology questioned the role of GitLab in submission, stating why not send a code zip file to Nexus or MRMP (Model validation tool)
3) Some methodology thinks its fine if Git can automated the removal of histories. (i.e. git export then git import to a new repo)
MRMC Requirement and Proposal:
On Git accesses:
1)  Methodology assumes default Guest access to Methodology GitLab, When raising the topic Methodology may not wish to grant Guest access, they suggested to create a seperate GitLab area named "Methodology Submission", where methodology can Write access and MRMC have Read access. 
2) Model Valudation is happy to grant Write access to Methodology on MRMC Repo. 
On Submission propsal
1) Methodology create sumbissoion tags either in Methodology Repo or "Mehtodology submission" Repo. 
2) Methodology in MRMC Repo create an empty sumbission Repo for his/her project. then requested to softlink to Methodology  repo using "git submodule" command to a folder called "Submission". the Model validation can checkout different submission tags when cd into "Submission" folder. This puts a Model Validation has READ access to the methodology repo. 
3) If a model have serveral components having their own respective Repos. They need to be consolidated into one repo.
Model IT Requirement
 On Code Development: 
1) IT thinks it is essential for them to continue in paritipating in code development. Either by have WRITE access to methodology repo, or they are fine to fork to IT repo / personal repo for development. 
2) They are fine not be able to perform merge to main branch. 
On CICD Build
1) IT would like to continue owning the CICD build and GIt Automation process in methodology repo.
 2) They are fine they do not have rights to perform production artifect build. 
On Git Access
1) For code development, Ideally to have Developer access to methodolgoy gitlab, if not, fine to have Guest access to fork to IT / Personal repo. 
2) Need at least one IT to have Developer access to maintain the CICD pipeline automation. 

RiskLab Model Service IT Requirement: 
On CICD Build:
For Methodology who wish to maintain CICD process, Model Service IT Innovator will template a common pipeline for all models and assist methodology for future maintainance. 
On Process standardization:
In order to support genric CICD template and standardized production docker generation, following changes to the model code is mandatory: 
1) Model lib dependency management: For R, use Renv for dependency management, For Pyhon, use Poetry for dependency management. 
2) Use RiskLab Model team supplied Companion production base image for docker build, each companion production base image is certified to be identical in OS and system libs to Risklab development enviorment used for model development. 
3)  If a model has components in seperate repos, they need to be merged into a single methodology repo for 1) Submission granularity, 2) ease of tempalting. 
4) If above 3 are met, Model Service IT Innovator could provide an easy to maintain Dockerfile and CICD template for mehtodology to adopt. 
On Process Automation: 
Model Service IT Innovator can initiate project for GitLab prcoess automation, for example using python-gitlab api, Question: Does GitLab exposes its GitLab server API?
 












