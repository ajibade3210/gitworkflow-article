#### Debug WorkFlow

Set Repository Secrets to see more log information to debug.
-   ACTIONS_RUNNER_DEBUG - true
-   ACTIONS_STEP_DEBUG - true

#### CHange M/C Shell
- use the **shell** key to inform gitaction that a job should run on a specific shell.

Jobs run in parallel on a seperate virtual m/c.
In order to make a job run in series or make a job wait for another job to complete use the **needs** key


#### Using an Actions.
Actions are some code we or someone else has written that does some specify task, that we can use in our steps in our git workflow.

By having actions we can write less codes. 

- To use an Action use the **uses** key word.
- To provide input for actions use the **with** keyword

Jobs step can return actions outputs...
To read an action output will
- first of give the step an **id**
- then we can `echo "${{ steps.greet.outputs.time }}"`

