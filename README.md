# Task Tools

This repository contains bash command line tools which should
provide hierarchy and calendar reports for task warrior tasks. 

## thrchy

This bash script lists tasks arranged by their dependencies (blocking, blocked).

### Dependencies:

* [jq](http://stedolan.github.io/jq/).

### Usage

* Listing tasks:
  `thrchy [ids] [all]`
    * `ids` are one or more space separated task ids.
    * The optional parameter `all` lists also completed tasks.
    * Examples: 
        * `thrchy 23`
        * `thrchy 23 34 5`
* Adding new dependent task:
  `thrchy [id] add [..normal task warrior commands..]`
    * `id` is the task id which should depend on the newly created task.
    * Examples: 
        * `thrchy 23 add +tag +tag2 subject description text prio:H`
        * `thrchy 23 add new task description`
* Change task dependency:
  `thrchy [id] move [parent_id]`
    * `id` is the task id which should be blocking another task.
    * `parent_id` is the task id which should be depending on `id`.
    * Examples: 
        * `thrchy 23 move 39`

## tcal

This tool shows tasks which are scheduled for the current week.

### Dependencies:

* gnu date util (on mac os install it via homebrew)

### Usage

* Usage: `tcal [week] [..task warrior filters..] [..task warrior report..]
* Usage Examples:
    * show tasks which are scheduled for the current week:
      `tcal`
    * show tasks which are scheduled for a specific week:
      `tcal 08`
      `tcal 08,09,10`
    * show tasks which are scheduled for current and next week:
      `tcal +1`
    * show tasks which are scheduled for previous and current week:
      `tcal -1`
    * show tasks which are scheduled for today:
      `tcal today`
    * show tasks which are scheduled for a specific date:
      `tcal 2015-01-01`
    * any valid task warrior filters can be specified after the optional week specifier:
      `tcal -1 +tag1 +tag2 proj:name prio:H`
    * any report can be specified in order to change the output:
      `tcal +1 minimal`

## tlog

This tool should provide a way to list time which was spent on certain issues.

ISSUE: still need to solve an issue due to differences between the bsd date and gnu date utility.

