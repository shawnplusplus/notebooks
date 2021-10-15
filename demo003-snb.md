## Pin Dockerfile Base Image


```
#language-agnostic #security #good-for-batch-changes #good-for-code-monitoring
```



### Use Case

Security Engineers or DevOps teams want to find all Dockerfiles that are using a "FROM &lt;baseimage>:latest" rather than a specific tag or SHA256 reference.

This is outlined in [Snyk's top 10 security best practices for Docker](https://snyk.io/blog/10-docker-image-security-best-practices/) (see #6).


### Description

This example is a great one to use for searching plus campaigns and code monitoring.  It is quick to run and very easy to understand.


### Steps


#### Basic Regex



* **<code>file:/Dockerfile FROM\s+.*:latest </code></strong>[[sg](https://demo.sourcegraph.com/search?q=file:/Dockerfile+FROM%5Cs%2B.*:latest&patternType=regexp)]

    This example is super easy to remember and to type when doing a quick demo with someone.  But it isn't quite as accurate as it needs to be.  For example, this will actually find results that are already pinned to a specific SHA256 (because we stopped at :latest).



#### More Accurate Regex



* **<code>file:/Dockerfile FROM (\w+\/)?\w+:latest($|\s) </code></strong>[[sg](https://demo.sourcegraph.com/search?q=file:/Dockerfile+FROM+%28%5Cw%2B%5C/%29%3F%5Cw%2B:latest%28%24%7C%5Cs%29&patternType=regexp)]


