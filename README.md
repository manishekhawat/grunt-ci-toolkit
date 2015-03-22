# grunt-standard-tasks
Repository to provide Standard Grunt Tasks for a project to support Front-end development.

Code Quality being an integral part of any organisation's front-end development process, each one of developer must follow a standard automated code quality tool. Grunt is one of the globally acknowledged tool that helps controlling code quality by it's task system.

A better development workflow can definitely improve efficiency and quality of projects, this Project has some Grunt task Aliases that will help projects to setup and work with consistent grunt tasks. Focus of this project is to make development workflow capable of capturing code errors while we develop HTMLs, CSS and JS functionalities. W3C testing, Accessibility Testing, JS/CSS Code quality checks are some of highlights of this program. Existing projects should be able to integrate these automation tests like W3C and accessibility on their CI environments and generate the reports in easy HTML formats.

## Getting Started
This package requires Grunt `~0.4.1`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may clone this repository and start using various listed below standards grunt tasks for your project.

## Task Aliases

### default
This task will not run any default task rather it is created to help a new developer in team. Running default task using command 'grunt' will prompt developer to select grunt tasks from the available tasks in gievn project. This task will generate all the available tasks in form of checkbox options configured under "PROMPT" tasks in Gruntfile.js file. User should be able to select and run any of the grunt task by hitting "space" key to select and "return" key to run the selected tasks.

Note: Any New Task or Alias should be updated in Gruntfile.js under "PROMPT" task.

```shell
? Which Grunt tasks would you like to run? 
 ──────────────
 ◯ Validate All js    ── Validate All JS files as configured in Gruntfile
 ◯ Validate Specific js       ── Validate specific JS files provided by User as text Input
 ◯ Validate Selected js       ── Validate specific JS files provided by User from provided list
 ◯ W3C Validation       ── Validate specific URLs provided by User for W3C and Generate Report in HTML Format
 ◯ Grunt for dev       ── Run Grunt for Dev tasks
 ◯ Grunt for Prod       ── Run Grunt for Prod tasks
 ──────────────
❯◯ Help           ── Show the Grunt tasks available
```

### validatealljs
Running 'validatealljs' task by 'grunt validatealljs' command or by selecting from grunt options will validate all the JS files with rules mentioned in '.jshintrc' file. This will validate all the JS files configured in JSHINT task option with variable '<b>jsFilesToBeValidated</b>'.

### validatejs
Running 'validatejs' task by 'grunt validatejs' command or by selecting from grunt options will validate all the JS files with rules mentioned in '.jshintrc' file. This task will Prompt developer to provide JS file names in a Textbox and then same will be validated to generate the report. Multiple file names can be provided with a space like js/test.js js/test1.js

### validateselectedjs
Running 'validateselectedjs' task by 'grunt validateselectedjs' command or by selecting from grunt options will validate all the JS files with rules mentioned in '.jshintrc' file. This task will Prompt developer to select JS file names in form of Checkbxes and files list will be generated by files configured in JSHINT option with variable '<b>jsFilesToBeValidated</b>'. Selection of files can be made by Space 'key' and then can be run by 'return' key.

Note: For other standard JSHINT options please refer to https://github.com/gruntjs/grunt-contrib-jshint

### validation
Running 'validation' task by 'grunt validation' command or by selecting from grunt options will validate all the configured URLs for W3C and generate the report.

Note: For detailed options please refer the original plug-in https://github.com/vikash-bhardwaj/grunt-w3c-html-validation

### dev
Running 'dev' task by 'grunt dev' command or by selecting from grunt options will run below tasks in defined order:
		"validatealljs",
    	"concat",
    	"cssmin",
    	"validation"

### prod
Running 'prod' task by 'grunt prod' command or by selecting from grunt options will run below tasks in defined order:
		"validatealljs",
    	"concat",
    	"cssmin",
    	"uglify",
    	"validation"

### help
Running 'help' task by 'grunt attention' command or by selecting from grunt options will show the available grunt commands/tasks on screen for new developers help. This will be similar to:

```shell
  ╔═════════════════════════════════════════════════════════════════════════╗
  ║                                                                         ║
  ║  // Gruntfile Automation                                                ║
  ║  Copyright 2015, Vikash Bhardwaj <vikasbhardwaj7@gmail.com> // The      ║
  ║  MIT License (MIT)                                                      ║
  ║                                                                         ║
  ║  There is no default task registered for Grunt.                         ║
  ║  Please use one of the following tasks:                                 ║
  ║                                                                         ║
  ║  .    .                                                                 ║
  ║  .    ├──┬─ $ grunt validatealljs                                       ║
  ║  .    │  └─ $ grunt validatejs                                          ║
  ║  .    │  └─ $ grunt validateselectedjs                                  ║
  ║  .    │  └─ $ grunt Validation                                          ║
  ║  .    │  └─ $ grunt dev                                                 ║
  ║  .    │  └─ $ grunt prod                                                ║
  ║                                                                         ║
  ╚═════════════════════════════════════════════════════════════════════════╝
```