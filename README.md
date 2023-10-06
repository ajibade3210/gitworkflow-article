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

schedule:
    - cron: "0/5 * * * *"
    - cron: "0/6 * * * *"

##### Filter Pattern Cheat Sheet
You can use special characters in path, branch and tag filters.

* `*``: Matches zero or more characters,  but does not match the / character. For example, `Octo*` matches `Octocat.
* `**`: Matches zero or more of any character.
* `?`: Matches zero or one single character. For example, `Octoc?t` matches `Octocat`.
* `+`: Matches one or more of the proceeding character.
* `[]`: Matches one character listed in the brackets or included in ranges. Ranges can only include `a-z`, `A-z`, and `0-9`. For example, the range  `[0-9a-f]` matches any digit or lowercase letter. For example, `[CB]at` matches `Cat` or `Bat` and `[1-2]00` matches `100` and `200`.
* `!`: At the start of a pattern makes it negate previous positive patterns. It has no special meaning if not the first character.

The characters `*`, `[]`, and `!` are special characters in YAML. If you start a pattern with `*`, `[]`, and `!`, you must enclose the pattern in quotes.

[filter-pattern-cheat-sheet](https://help.github.com/en/actions/automating-your-workflow-with-github-actions/workflow-syntax-for-github-actions#filter-pattern-cheat-sheet)


