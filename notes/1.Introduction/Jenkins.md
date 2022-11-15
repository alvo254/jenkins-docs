Jenkins Pipelines is a group of plugins that support the integration and implementation of continuous delivery pipelines.
Jenkins provides you with two ways of developing your pipeline code: Scripted and Declarative. Scripted pipelines, also known as “traditional” pipelines, are based on Groovy as their Domain-specific language. On the other hand, Declarative pipelines provide a simplified and more friendly syntax with specific statements for defining them, without needing to learn Groovy.

### Declarative Pipelines Syntax

A valid Declarative pipeline must be defined with the “pipeline” sentence and include the next required sections:

-   agent
-   stages
-   stage
-   steps