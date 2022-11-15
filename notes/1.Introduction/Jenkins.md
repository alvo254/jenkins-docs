Jenkins Pipelines is a group of plugins that support the integration and implementation of continuous delivery pipelines.
Jenkins provides you with two ways of developing your pipeline code: Scripted and Declarative. Scripted pipelines, also known as “traditional” pipelines, are based on Groovy as their Domain-specific language. On the other hand, Declarative pipelines provide a simplified and more friendly syntax with specific statements for defining them, without needing to learn Groovy.

### Declarative Pipelines Syntax

A valid Declarative pipeline must be defined with the “pipeline” sentence and include the next required sections:

-   agent
-   stages
-   stage
-   steps

Also, these are the available directives:

-   environment (Defined at stage or pipeline level)
-   input (Defined at stage level)
-   options (Defined at stage or pipeline level)
-   parallel
-   parameters
-   post
-   script
-   tools
-   triggers
-   when

### Agent

Jenkins provides the ability to perform distributed builds by delegating them to “agent” nodes. Doing this allows you to execute several projects with only one instance of the Jenkins server, while the workload is distributed to its agents. Details on how to configure a master/agent mode are out of the scope of this blog. Please refer to [Jenkins Distributed builds Links to an external site.](https://wiki.jenkins.io/display/jenkins/distributed+builds)for more information.

Agents should be labeled so they can be easily identified from each other. For example, nodes can be labeled by their platform (Linux, Windows, etc), by their versions or by their location, among others. The “agent” section configures on which nodes the pipeline can be run. Specifying “agent any” means that Jenkins will run the job on any of the available nodes.

pipeline {  
 agent any  
 ...  
}

### Stages

This section allows us to generate different stages on your pipeline that will be visualized as different segments when the job is run.

A sample pipeline including the stages sentence is provided:

pipeline {  
 agent any  
 stages {  
 ...  
 }  
}  
 

### Stage

At least one “stage” section must be defined in the “stages” section. It will contain the work that the pipeline will execute. Stages must be named accordingly since Jenkins will display each of them on its interface. 

Jenkins graphically splits pipeline execution based on the defined stages and displays their duration and whether it was successful or not.

A pipeline script might look like the following:

pipeline {  
 agent any  
 stages {  
 stage ('build') {  
 ...  
 }  
 stage ('test: integration-&-quality') {  
 ...  
 }  
 stage ('test: functional') {  
 ...  
 }  
 stage ('test: load-&-security') {  
 ...  
 }  
 stage ('approval') {  
 ...  
 }  
 stage ('deploy:prod') {  
 ...  
 }  
 }  
}