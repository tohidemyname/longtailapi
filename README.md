# An Empirical Study on the Long-tail Distribution of APIs

##Summary

APIs are intensively called in source files and are critical in development. To assist programming with APIs, researchers have proposed various approaches, which cover a wide range of research topics. With the recent advances in machine learning, most approaches are learning-based and need to observe many instances. Although they achieve good results in their evaluations, programmers complain that these approaches are not as effective as reported. In the security research community, we hear similar complaints about malware detection. 

A highly cited study identifies that the complaints are partially caused by the different distributions between benchmarks and the wild. In the wild, only a small port of applications is malware, but most benchmarks contain almost the same number of malware and benign applications. When the distribution is changed, this study shows that the effectiveness of malware detectors is significantly reduced. The complaints about API-related approaches can be caused by similar reasons. However, there is no consensus on the distribution of API calls. Like malware, libraries have cold spots and hot spots. The effectiveness of learning-based approaches will be significantly reduced, if they have few instances for learning. Although these approaches work poorly on infrequent APIs, many researchers blindly believe that cold spots will ablate if more projects are introduced. As a result, even if many examples are presented to show that APIs from cold spots can be more useful than those from hot spots, many researchers criticize that there is no need for researching infrequent APIs since they believe that cold spots will ablate with more projects. The blind assumption hinders the research on infrequent APIs. To explore whether this assumption holds, in this paper, we conduct an empirical study. 

##Dataset

We extract API calls from the following projects:

| Project          | URL                                                 | Commit                                   |
| ---------------- | --------------------------------------------------- | ---------------------------------------- |
| poi              | https://github.com/apache/poi                       | 908fb7f9f93fbcba63c8cf055d4d2b413b04f1a5 |
| dubbo            | https://github.com/apache/dubbo                     | d452ea492424ab470c2b2a47e4a5338d4dd6612b |
| cassandra        | https://github.com/apache/cassandra                 | 48417940280021d0012b7a7db6c9f823a98086e4 |
| lucene           | https://github.com/apache/lucene                    | 2bd87b79090c9a0e9d5d9d195e109991740831cd |
| jmonkeyengine    | https://github.com/jMonkeyEngine/jmonkeyengine      | 179fd66b7bbded86b109f9ba23de49b4ca6525e5 |
| asm              | https://gitlab.ow2.org/asm/asm                      | 9bf7d41ca5212d82b6383104d3340d3e897fea42 |
| guava            | https://github.com/google/guava                     | 641d9e682be2468dc2afa74ded4af0ae7455f8d0 |
| spring-framework | https://github.com/spring-projects/spring-framework | feac983869ce13579aca13266c72b5171f1e03a3 |
| azure            | https://github.com/Azure/azure-sdk-for-java         | ba4ae0bfb042b563b6e65c3a843deddffe5b4827 |

The extracted API calls are listed in the folder of each project.
