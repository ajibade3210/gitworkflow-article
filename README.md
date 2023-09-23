#### Debug WorkFlow

Set Repository Secrets to see more log information to debug.
-   ACTIONS_RUNNER_DEBUG - true
-   ACTIONS_STEP_DEBUG - true

#### CHange M/C Shell
- use the `shell` key to inform gitaction that a job should run on a specific shell.

Jobs run in parallel on a seperate virtual m/c.
In order to make a job run in series or make a job wait for another job to complete use the `needs` key