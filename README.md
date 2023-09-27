#### Debug WorkFlow

Set Repository Secrets to see more log information to debug.

-   ACTIONS_RUNNER_DEBUG - true
-   ACTIONS_STEP_DEBUG - true

#### CHange M/C Shell

-   use the **shell** key to inform gitaction that a job should run on a specific shell.

Jobs run in parallel on a seperate virtual m/c.
In order to make a job run in series or make a job wait for another job to complete use the **needs** key

#### Using an Actions.

Actions are some code we or someone else has written that does some specify task, that we can use in our steps in our git workflow.

By having actions we can write less codes.

-   To use an Action use the **uses** key word.
-   To provide input for actions use the **with** keyword

Jobs step can return actions outputs...
To read an action output will

-   first of give the step an **id**
-   then we can `echo "${{ steps.greet.outputs.time }}"`

#### Cloning Repository

By default github does not clone our repository into out git action folder. To do this we will make use of an action provided to us by git. **@checkout**

this authenticate with the repository, fetchs the code then checkout out into the gitaction folder.

##### Actions MarketPlace
Using external actions...


#### Events, Schedules, External Events
Adding [push, pull_request] event

pull_request:
    types: [closed, assigned, opened, reopened]

Some events have types Push doesn’t, but PR has, We can use the PR types to set when the workflow should run whether on opened/closed, or we we assign a reviewer, or reassign, or reopen

https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows

##### Schedules
To set the schedule
Use the schedule object key. Which will contain a Cron Array.
In quotation a CRON schedule expression contains:
"min hrs dayOfMnth mnth dayOfWeek"
