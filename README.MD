# Simple C++ Logger
This is a simple logger, it can log to a terminal or to a file.
If macro-version is used it will log the current date and time.
* LOG_TO_FILE doesnt log anything to terminal and vice-versa.
* Logger() << is mean to work like qDebug() does.

## Usage
```cpp
Logger() << "Simple message just like qDebug()";
LOG_TO_FILE(Logger::Severity::Info, "logs.log", "This is an info to be written to a file");
LOG_TO_TERMINAL(Logger::Severity::Error, "An error example");
LOG_ASSERT(false, "Program stops if argument is false but if true nothing is shown");
```
Where Logger::Severity is an enumeration just like:
```cpp
typedef enum Severity
{
	Trace = 0,
	Info,
	Warn,
	Error,
	Assert
} Severity;
```

The output of that example will be:

```bash
terminal: Simple message just like qDebug()
logs.log: [20/12/2022 - 17:15:11][Main.cpp - 71][Info]: This is an info to be written to a file
terminal: [20/12/2022 - 17:15:11][Main.cpp - 72][Error]: An error example
terminal: [20/12/2022 - 17:15:11][Main.cpp - 73][Assertion]: Program stops if argument is false but if true nothing is shown
```
