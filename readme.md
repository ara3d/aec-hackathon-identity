# Team Identity

## Entry for AEC Hackathon, February 2024 in Zurich

## Members 

* Ahmed Wael Ismail
* Christopher Diggins 
* Elia Waefle 
* Helena Krogmann 
* Mohammed Khazna 
* Olga Poletkina 
* Otmane Salih 

## Problem Statement 

What is called a BIM model, is actually a disparate set of documents stored in different CDEs, with lots of replication.
Communicating and collaborating between stakeholders and teams requires a complex and inaccurate process involving conversions of files.

One of the biggest challenges is having a common understanding of when two documents or issues are talking about the same thing. 
In other words there is no widely-agreed upon mechanism for a project to have a central authority to identify the entities. 

## Our Proposed Solution 

Our proposal was to build an **Identity Model** in a text-readable format (e.g., JSON) which provides linkage between the different 
chunks of data (**components**) and the different documents.

By storing the entity and component data in plain-text, we can use use the same text-based version control tools that developers use
such as VS code, Git, and Github.

## VS Code Integrated Diffing Tool

![image](https://github.com/ara3d/aec-hackathon-identity/assets/1759994/4d408f2c-8e8d-4a27-95d3-c8fc986f7cfa)

## Github Workflows

![image](https://github.com/ara3d/aec-hackathon-identity/assets/1759994/e86366e3-fb33-44ae-a2b5-34f00362f508)
![image](https://github.com/ara3d/aec-hackathon-identity/assets/1759994/0eeb96cb-b14c-4049-983e-a5a46e038752)

## Displaying Changes in Revit - With Approval

Beyond using existing tools, by storing it in an easily parsed format like JSON, it is possible to quickly write new tools
that can compute deltas between identity models and show the differences directly in the BIM authoring tool:

https://github.com/ara3d/aec-hackathon-identity/assets/1759994/2c289d1c-a809-4aba-b223-b6172bc2cb20

## Displaying Changes in Rhino - Before Sending

We can also provide better controls for people making changes to send (commit) data when it make sense: 

https://github.com/ara3d/aec-hackathon-identity/assets/1759994/9a5fbaae-45fc-49e6-bb6d-047039c3eb43

## Presentation

* [https://github.com/ara3d/aec-hackathon-identity/blob/main/identy.pptx]
* [https://github.com/ara3d/aec-hackathon-identity/blob/main/identy.pdf]

## Technical Challenge: Mesh Similarity

One of the technical hurdles is dealing with similarity with meshes. For the purpose of the Hackathon
we developed some code in C# to compute mesh similarity.

![image](https://github.com/ara3d/aec-hackathon-identity/assets/1759994/04d5372e-2a36-4de8-a5b5-c9b76b8e2d99)

## Code Links 

Some of the code for the hackathon can be found as part of the Ara3D repository online at:

* https://github.com/ara3d/ara3d/tree/main/labs/Identification
* https://github.com/ara3d/ara3d/tree/main/labs/IdentificationApp

These folders contains libraries of C# functions for:

* Generating an initial identity model in JSON format
* Computing difference between two identity models as an array of JSON records 

## Other Code Written 

The following code examples have not yet been uploaded online: 

* A Python script for Revit was written by Olga Poletkina to read JSON difference records
* A Rhino plug-in was written by Ahmed Wael Imsail to generate a list of OBJs from Rhino
* A Python standalone script was written by Elia Waefle to generate a list of OBJ files and JSON parameter sets  

## References

* [Strange Matter by Greg Schelussner](https://github.com/magnetar-io/strange_matter)
