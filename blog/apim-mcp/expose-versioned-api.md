# Step 1 - Non versioned API as MCP

When we expose a non-versioned API as MCP server (use case CW2), everything works as expected.

<img width="3417" height="1177" alt="image" src="https://github.com/user-attachments/assets/1227726b-ae8c-4d58-acd0-a7ebb30821df" />

# Step 2 - Versioned API as MCP

If we expose a versioned API as MCP server, we can connect to the MCP, explore the tools, but when we invoke the tools we got a 404, because as explained here : https://learn.microsoft.com/en-us/answers/questions/5657980/azure-apim-mcp 
the MCP server perform a downstream call by using ```baseURL + operation``` instead of ```baseURL + version identifier + operation```

<img width="3427" height="1073" alt="image" src="https://github.com/user-attachments/assets/74362c7c-226e-402d-ad1a-df5c16b5c3d1" />


# Step 3 - Suggested solution (not working)

When we tried the suggested solution the MCP server does not start.

<img width="3360" height="1122" alt="image" src="https://github.com/user-attachments/assets/a7ef60a5-25f6-4aaf-95d4-07c8866099c9" />

We tried to setup a different backend service using multiple approaches (specify the url, using backend id, etc...) but no way to connect to the MCP server with a policy different than ```<base/>```

# Step 4 - (not good) Workaround

The only way to get this scenario working is to apply the following (very bad) workaround, moving the path-based version segment into the base URL and make the version identifier empty.
Clearly not a future proof solution

<img width="3414" height="1039" alt="image" src="https://github.com/user-attachments/assets/5674b0a6-fa07-4e08-9b6f-80ebb61602fb" />


Looking forward for a better way to get this scenario working.
