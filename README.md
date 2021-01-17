# Requirements

```
pip3 install jira
pip3 install urwid
```

# Introduction

If you're confused like me when accessing Jira web GUI, and would like faster
and easier way to access it without leaving the comfort of your terminal, then
you might find this little tool helpful.

# Run

```
jira
```

Running the above command will bring up the ncurses GUI.
The top list is a predefined set of filters that you can extend (see filters
section below). You can also specify any filter from the GUI.

# Panes

| Pane			| Usage						|
|-----------------------|-----------------------------------------------|
|Filters		| List of predefined filters			|
|Filter			| The text of the filter executed. You can modify this or run any other non-predefined filter you want following jira syntax.	|
|View Issue		| Type any issue and press enter to view it	|
|Issues			| List of issues returned by the executed filter. We return all issues, jira can be slow if your query returns a large list. Mainly becaues the server is slow.	|


# Navigation

vim like binding is available.

| Key			| Action					|
|-----------------------|-----------------------------------------------|
|UP, j, CTRL-p		| Move the cursor up				|
|DOWN, k, CTRL-n	| Move the cursor down				|
|g, Home		| Move the cursor top				|
|G, End			| Move the cursor bottom			|
|PAGE-UP, CTRL-u	| Move the cursor one page up			|
|PAGE-DOWN, CTRL-d	| Move the cursor one page down			|
|F			| Move the cursor to Filters list pane		|
|f			| Move the cursor to Filter text pane		|
|V			| Move the cursor to View Issue text pane	|
|I			| Move the cursor to Issues list pane		|
|q,Q			| Close any viewed issue / exit app		|

# Custom Filters

You can add your own customer filter to: $HOME/.jira/filters

Each entry must have a:

* name
* filter

fields. And an optional:

* order_by

if no order_by specified the global order_by will be used.

# Limitations

* If you failed to open an issue, it means there's a bug that's causing an
  exception but we silently ignore it.
* It is Read-Only.
