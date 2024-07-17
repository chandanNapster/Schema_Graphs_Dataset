# Supplementary Material for Schema-based query optimisation for Graph Databases

The contents of this repository are dedicated to providing detailed information regarding the datasets, schemas, and queries utilized to carry out the experiments for the research paper titled "Schema-based query optimization for graph databases". By exploring this repository, one can understand the datasets, graph structures, and queries employed in this research.

## Table of content

* [Dataset](#dataset)
* [Schema](#schema)
* [Queries](#queries)



## Dataset 
We consider datasets of different nature:

### YAGO
We consider [YAGO2s](https://yago-knowledge.org/downloads/yago-2s) a real knowledge graph. We use the cleaned version of the real-world dataset YAGO2s in which only nodes with unique identifiers are present. We split the set of RDF triples into multiple edge relations (tables), one for each predicate name. We create a node relation (table) for each node class.

### LDBC-SNB
 The Social Network Benchmark (SNB) interactive workload from the Linked Data Benchmark Council [(LDBC)](https://ldbcouncil.org) is a synthetic reference benchmark for property graphs. Specifically, we used the LDBC-SNB dataset in CSV format provided by [LDBC-SNB](https://repository.surfsara.nl/datasets/cwi/snb). We consider six scale factors of LDBC-SNB, particularly scale factors 0.1, 0.3, 1, 3, 10 and 30. 

Sample files for scale factors 0.1 and 0.3 have been provided at [LDBC sample dataset](/Dataset/LDBC/).  
<!-- In this study, the YAGO and LDBC-SNB datasets are a collection of data that comprise node and edge relations. Node relations are designated with the prefix NR and describe the properties of individual nodes, while edge relations are designated with the prefix ER and describe the connections between nodes. -->

## Schema
We have created graph schemas specifically for the YAGO and LDBC-SNB datasets that assist in schema-based query optimisation. To enhance user understanding and visualization, we provide graph schemas for YAGO and LDBC-SNB datasets in PDF format at [Schemas](/Schema/Graph_Schema_for_VLDB.pdf).
### YAGO

YAGO, a knowledge graph, does not come with a graph schema. As a result, we have created a basic graph schema for YAGO that is presented in [Schemas](/Schema/Graph_Schema_for_VLDB.pdf). The YAGO schema is based on the [SHACL semantic constraints for YAGO](https://arxiv.org/abs/2308.11884). The YAGO graph schema, developed as a part of this study, is available in a serializable format at [YAGO Schema](/Schema/Graph_schema_YAGO_Serializable.txt).

### LDBC-SNB
The LDBC-SNB dataset comes with a [pre-defined property graph schema](https://doi.org/10.1145/2723372.2742786) that outlines the structure and relationships of the dataset's entities. This schema is an essential aspect of the study and helps to organize and understand the data. The LDBC-SNB graph schema used in this study is available in a serializable format at [LDBC Schema](/Schema/Graph_Schema_LDBC_Serializable.txt).


## Queries
Through our experimental analysis, we have investigated different queries with unique characteristics. Our focus has been on two primary types of queries: acyclic and cyclic-shaped. Queries can be further classified as either recursive or non-recursive. Recursive queries use the Kleene plus operation, allowing graph pattern repetition. On the other hand, non-recursive queries do not use the Kleene plus operation and, therefore, cannot repeat graph patterns.


### YAGO
Our research examined 18 queries on the YAGO dataset, all acyclic-shaped recursive graph queries. We have made the YAGO initial and schema-based rewritten queries available in this repository for easy access. You can find them at the following links: [YAGO initial queries](/Queries/UCQT_Initial_Query_YAGO.csv) and [YAGO schema-based rewritten queries](/Queries/UCQT_Schema_Based_Rewritten_YAGO.csv).


### LDBC-SNB
We analyzed 30 queries on the LDBC-SNB dataset. Of these 30 queries, 12 were non-recursive, while 18 were recursive. Additionally, we found that 21 queries were acyclic, while the remaining 9 queries had cyclic shapes. We have provided the initial and schema-based rewritten queries of the LDBC-SNB dataset in this repository for more details. You can access these files by visiting the following links: [LDBC-SNB initial queries](/Queries/UCQT_Initial_Query_LDBC.csv) and [LDBC-SNB schema-based rewritten queries](/Queries/UCQT_Schema_Based_Rewritten_LDBC.csv).








<!-- ## Getting started

To make it easy for you to get started with GitLab, here's a list of recommended next steps.

Already a pro? Just edit this README.md and make it your own. Want to make it easy? [Use the template at the bottom](#editing-this-readme)!

## Add your files

- [ ] [Create](https://docs.gitlab.com/ee/user/project/repository/web_editor.html#create-a-file) or [upload](https://docs.gitlab.com/ee/user/project/repository/web_editor.html#upload-a-file) files
- [ ] [Add files using the command line](https://docs.gitlab.com/ee/gitlab-basics/add-file.html#add-a-file-using-the-command-line) or push an existing Git repository with the following command:

```
cd existing_repo
git remote add origin https://gitlab.inria.fr/tyrex-public/schema-graph-query.git
git branch -M main
git push -uf origin main
```

## Integrate with your tools

- [ ] [Set up project integrations](https://gitlab.inria.fr/tyrex-public/schema-graph-query/-/settings/integrations)

## Collaborate with your team

- [ ] [Invite team members and collaborators](https://docs.gitlab.com/ee/user/project/members/)
- [ ] [Create a new merge request](https://docs.gitlab.com/ee/user/project/merge_requests/creating_merge_requests.html)
- [ ] [Automatically close issues from merge requests](https://docs.gitlab.com/ee/user/project/issues/managing_issues.html#closing-issues-automatically)
- [ ] [Enable merge request approvals](https://docs.gitlab.com/ee/user/project/merge_requests/approvals/)
- [ ] [Set auto-merge](https://docs.gitlab.com/ee/user/project/merge_requests/merge_when_pipeline_succeeds.html)

## Test and Deploy

Use the built-in continuous integration in GitLab.

- [ ] [Get started with GitLab CI/CD](https://docs.gitlab.com/ee/ci/quick_start/index.html)
- [ ] [Analyze your code for known vulnerabilities with Static Application Security Testing (SAST)](https://docs.gitlab.com/ee/user/application_security/sast/)
- [ ] [Deploy to Kubernetes, Amazon EC2, or Amazon ECS using Auto Deploy](https://docs.gitlab.com/ee/topics/autodevops/requirements.html)
- [ ] [Use pull-based deployments for improved Kubernetes management](https://docs.gitlab.com/ee/user/clusters/agent/)
- [ ] [Set up protected environments](https://docs.gitlab.com/ee/ci/environments/protected_environments.html)

***

# Editing this README

When you're ready to make this README your own, just edit this file and use the handy template below (or feel free to structure it however you want - this is just a starting point!). Thanks to [makeareadme.com](https://www.makeareadme.com/) for this template.

## Suggestions for a good README

Every project is different, so consider which of these sections apply to yours. The sections used in the template are suggestions for most open source projects. Also keep in mind that while a README can be too long and detailed, too long is better than too short. If you think your README is too long, consider utilizing another form of documentation rather than cutting out information.

## Name
Schema-based Query Optimisation for Graph Databases - Supplementary material

## Description
Let people know what your project can do specifically. Provide context and add a link to any reference visitors might be unfamiliar with. A list of Features or a Background subsection can also be added here. If there are alternatives to your project, this is a good place to list differentiating factors.

## Badges
On some READMEs, you may see small images that convey metadata, such as whether or not all the tests are passing for the project. You can use Shields to add some to your README. Many services also have instructions for adding a badge.

## Visuals
Depending on what you are making, it can be a good idea to include screenshots or even a video (you'll frequently see GIFs rather than actual videos). Tools like ttygif can help, but check out Asciinema for a more sophisticated method.

## Installation
Within a particular ecosystem, there may be a common way of installing things, such as using Yarn, NuGet, or Homebrew. However, consider the possibility that whoever is reading your README is a novice and would like more guidance. Listing specific steps helps remove ambiguity and gets people to using your project as quickly as possible. If it only runs in a specific context like a particular programming language version or operating system or has dependencies that have to be installed manually, also add a Requirements subsection.

## Usage
Use examples liberally, and show the expected output if you can. It's helpful to have inline the smallest example of usage that you can demonstrate, while providing links to more sophisticated examples if they are too long to reasonably include in the README.

## Support
Tell people where they can go to for help. It can be any combination of an issue tracker, a chat room, an email address, etc.

## Roadmap
If you have ideas for releases in the future, it is a good idea to list them in the README.

## Contributing
State if you are open to contributions and what your requirements are for accepting them.

For people who want to make changes to your project, it's helpful to have some documentation on how to get started. Perhaps there is a script that they should run or some environment variables that they need to set. Make these steps explicit. These instructions could also be useful to your future self.

You can also document commands to lint the code or run tests. These steps help to ensure high code quality and reduce the likelihood that the changes inadvertently break something. Having instructions for running tests is especially helpful if it requires external setup, such as starting a Selenium server for testing in a browser. -->

<!-- ## Authors and acknowledgment
* [Chandan Sharma] chandan.sharma@inria.fr
* [Pierre Genevès] pierre.geneves@inria.fr
* [Nils Gesbert] nils.gesbert@inria.fr
* [Nabil Layaida] nabil.layaida@inria.fr

## Preprint
You can find the preprint version of this research paper on the INRIA HAL SCIENCE web portal by following this link: [INRIA HAL research paper link](https://inria.hal.science/hal-04485125). -->

<!-- ## License
For open source projects, say how it is licensed.

## Project status
If you have run out of energy or time for your project, put a note at the top of the README saying that development has slowed down or stopped completely. Someone may choose to fork your project or volunteer to step in as a maintainer or owner, allowing your project to keep going. You can also make an explicit request for maintainers. -->
