# vso-agent-tasks

## Installation

The [TFS Cross Platform Command Line utility (tfx-cli)](https://github.com/Microsoft/tfs-cli) is used to install tasks. It is built on Node.js, so if you have not already got Node.js you have to install it. 

Then, to install a task run the following commands in a Node.js command prompt:

* `npm install -g tfx-cli` - *This installs the tfx-cli tool.*
* `tfx login` - *The login is reused throughout the entire session.*
  * Enter collection url > `https://your.tfs-server.com/DefaultCollection`
  * Enter personal access token > `2lqewmdba7theldpuoqn7zgs46bmz5c2ppkazlwvk2z2segsgqrq` - *This is obviously a bogus token... You can add tokens to access your account at https://your.tfs-server.com/_details/security/tokens.* 
* `tfx build tasks upload --task-path c:\path-to-repo\vso-agent-tasks\JsonTokenReplacement`
  * *If you change your mind and do not want a task anymore, you can remove it with* `tfx build tasks delete b8df3d76-4ee4-45a9-a659-6ead63b536b4`, *where the Guid is easiest found in the task.json of your task.*

If you make a change to a task that you have previously uploaded, you have to bump its version before you upload it again. The server does not allow overwriting the content of an existing version.
