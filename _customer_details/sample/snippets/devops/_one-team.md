---
---
<!-- markdownlint-disable MD041 -->
**_Note:<br/>The following is a curated mix of illustrative findings from various anonymized reports_**

### Infrastructure information is for administrators only

Information regarding your infrastructure setup is hidden on a "secret" page, only accessible by administrators.

#### Open this information up for everybody (M)

Simply make this information public.
Prune or encrypt any confidential information or passwords stored there, but try to share as much knowledge with your peers.

#### Manage your secrets in a tool (S)

Consider using a tool like [vault](https://www.vaultproject.io/intro/index.html) to manage your secrets.
This would simplify your credential management in Jenkins as well, as it would simply get them from Vault through its simple API.
