# slash-command-processor-backend

Storage for any slash command-based (chatops) GitHub workflows used for backend software.

## Commands

**`/deploy`**

Deploys application to a specified cluster.

### Syntax
/deploy (cluster=<name>) [commit|branch=<id or name>] [chart-name=<name>]

### Examples

**Posting a comment inside an issue:**   
`/deploy cluster=erickube commit=xyz`  
`/deploy cluster=erickube branch=develop chart-name=foo`

**Posting a comment inside a pull request:**   
`/deploy cluster=siddkube`  
`/deploy cluster=siddkube commit=xyz`   
`/deploy cluster=siddkube chart-name=baaz`  

_If no commit is given in a PR comment, the head commit is used._

Repositories that use this command need to include a GitHub workflow that runs on issue comment
creation ([example](https://github.com/dictyBase/publication/blob/develop/.github/workflows/chatops.yml)).
