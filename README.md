# Task Tools

This repository contains bash command line tools which should
provide hierarchy and calendar reports for task warrior tasks. 

## thrchy

This bash script lists tasks arranged by their dependencies (blocking, blocked).

Dependencies:

* [jq](http://stedolan.github.io/jq/).

## Usage

* Listing tasks:</br>
  `thrchy [ids] [all]`
    * `ids` are one or more space separated task ids.
    * The optional parameter `all` lists also completed tasks.
    * Example: `thrchy 23`
* Adding new dependent task:</br>
  `thrchy [id] add [..normal task warrior commands..]`
    * `id` is the task id which should depend on the newly created task.
    * Example: `thrchy 23 add +tag +tag2 subject description text prio:H`
* Change task dependency:</br>
  `thrchy [id] move [parent_id]`
    * `id` is the task id which should be blocking another task.
    * `parent_id` is the task id which should be depending on `id`.

## tcal

This tool shows tasks which are scheduled for the current week.

ISSUE: still need to solve an issue due to differences between the bsd date and gnu date utility.

## tlog

This tool should provide a way to list time which was spent on certain issues.

ISSUE: still need to solve an issue due to differences between the bsd date and gnu date utility.

