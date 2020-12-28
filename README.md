# trunk based github actions

Testing github actions support of cicd with a trunk based branching strategy.

It's not currently in a state to start using in production. It's close, with environments and their approvals and the manual trigger (workflow_dispatch) features, but lacks the ability to run or rerun individual jobs. This feature is needed in order to rerun failed deployments and redeploy earlier releases.