# LogAnalyzer 


**LogAnalyzer** is a tool that helps you to manually analyze your log files by
reducing the content with regular expression patterns you define.

You are supposed to write regular expressions (*Ignore patterns*) for the parts
that should be removed from the text view until only the interesting parts are left.

And then there are regular expressions (*Report patterns*) that are used to
generate a report.

There is an extension for the content management system *eZ Publish (legacy)* to
download log files directly from the server.


## Features

- adding log files via drag and drop
- finding text in the log file with <kbd>Ctrl</kbd> + <kbd>F</kbd>
    - navigate with <kbd>F3</kbd> and <kbd>⇧</kbd> + <kbd>F3</kbd>
- adding of ignore patterns from selected text
    - use the shortcut <kbd>Ctrl</kbd> + <kbd>I</kbd>
    - use regular expressions as patterns
- adding of report patterns from selected text
    - use the shortcut <kbd>Ctrl</kbd> + <kbd>E</kbd>
    - use regular expressions as patterns
- searching for matching text of ignore patterns if you select them
- removing all matches of ignore patterns from the text
    - empty lines will be removed by default
- exporting and importing of ignore and report patterns
- moving of patterns via drag and drop
- reloading of current file with <kbd>Ctrl</kbd> + <kbd>R</kbd>
- filtering of patterns 
- generation of reports from the report patterns
- exporting of the report as PDF
- printing of the report



## Minimum software requirements
- A desktop operating system, that supports [Qt5](https://doc.qt.io/qt-5/)
- Qt 5.3+
- gcc 4.8+


