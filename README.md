# LangServe  🦜 🏓 on Lightning.AI ⚡️

## Deploy on Lightning
TBA

> :information_source: **Make sure to set your environmental variables (teamspace secrets)! **
<img width="661" alt="Screenshot 2024-03-29 at 10 53 51 AM" src="https://github.com/PaulLockettOrg/LangServe-lightning/assets/20708690/4cf5d3c9-f588-43ad-9301-02d46affff7e">

## Adding packages
Add the package to your local repo
```bash
# adding packages from 
# https://github.com/langchain-ai/langchain/tree/master/templates
langchain app add $PROJECT_NAME

# adding custom GitHub repo packages
langchain app add --repo $OWNER/$REPO
# or with whole git string (supports other git providers):
# langchain app add git+https://github.com/hwchase17/chain-of-verification

# with a custom api mount point (defaults to `/{package_name}`)
langchain app add $PROJECT_NAME --api_path=/my/custom/path/rag
```

Note: you remove packages by their api path

```bash
langchain app remove my/custom/path/rag
```

After adding the project to your local repo you need to add it to your project's
pyproject.toml

```bash
#
# other packages
$PROJECT_NAME = { path = "packages/$PROJECT_NAME" }
#
#
```

## Setup LangSmith (Optional)
LangSmith will help us trace, monitor and debug LangChain applications. 
LangSmith is currently in private beta, you can sign up [here](https://smith.langchain.com/). 
If you don't have access, you can skip this section


```shell
# add these to your lightning AI enviromental variables
LANGCHAIN_TRACING_V2=true
LANGCHAIN_API_KEY=<your-api-key>
LANGCHAIN_PROJECT=<your-project>  
# if not specified, defaults to "default"
```
