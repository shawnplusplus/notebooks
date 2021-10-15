## Find Secrets and Tokens


```
#language-agnostic #security #good-for-code-monitoring
```



### Use Case

You are looking through your code for any private keys or things that look like tokens.


### Steps


#### Regex Search



* **<code>("[a-z0-9+/]{32,}=?"|'[a-z0-9+/]{32,}=?'|`[a-z0-9+/]{32,}=?`) or -----BEGIN RSA PRIVATE KEY----- or token.+[a-z0-9+/]{32,}=['"]?\n lang:go </code></strong>[[sg](https://sourcegraph.com/search?q=+%28%22%5Ba-z0-9%2B/%5D%7B32%2C%7D%3D%3F%22%7C%27%5Ba-z0-9%2B/%5D%7B32%2C%7D%3D%3F%27%7C%60%5Ba-z0-9%2B/%5D%7B32%2C%7D%3D%3F%60%29+or+-----BEGIN+RSA+PRIVATE+KEY-----+or+token.%2B%5Ba-z0-9%2B/%5D%7B32%2C%7D%3D%5B%27%22%5D%3F%5Cn+lang:go&patternType=regexp)]
* <strong><code>(key|secret|token)-[\w+]{32,}</code></strong>


