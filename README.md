# CommandRegistry Library

The CommandRegistry library simplifies the implementation and management of commands in applications. This library allows developers to register, describe, and execute commands easily. The registry approach facilitates the integration of new commands, enhancing the flexibility and extensibility of applications.

## Features

- **Command Registration:** Easily register commands with descriptions and optional parameters.
- **Centralized Command Execution:** Provides a central interface for executing commands, promoting code consistency and maintainability.
- **Flexibility:** Supports dynamic addition and removal of commands, making it suitable for evolving applications.
- **User Interaction:** Ideal for applications requiring a command-line interface or similar interactive control.

## Getting Started

### Installation

You can download the CommandRegistry library from releases or build it yourself:

## Usage
### 1. Create a CommandCenter:
```csharp
  var commandProcessor = new CommandProcessor();
```

### 2. Add Commands:
```csharp
  commandProcessor.AddCommand(new CommandBuilder("example")
      .SetDescription("Example command")
      .SetAction(parameters =>
      {
          // Command logic here
          Console.WriteLine("Executing the example command!");
      })
      .Build());
```

### 3. Process Commands:
```csharp
  while (true)
  {
      Console.Write("Enter a command: ");
      string input = Console.ReadLine();
      commandProcessor.ProcessCommand(input);
  }
```
