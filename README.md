# CommandCenter Library

The CommandRegistry library simplifies the implementation and management of commands in applications. This library allows developers to register, describe, and execute commands easily. The registry approach facilitates the integration of new commands, enhancing the flexibility and extensibility of applications.

## Features

- **Command Registration:** Easily register commands with descriptions and optional parameters.
- **Centralized Command Execution:** Provides a central interface for executing commands, promoting code consistency and maintainability.
- **Flexibility:** Supports dynamic addition and removal of commands, making it suitable for evolving applications.
- **User Interaction:** Ideal for applications requiring a command-line interface or similar interactive control.

## Getting Started

### Installation

You can download the CommandCenter library from releases, NuGet or build it yourself:

```bash
dotnet add package CommandCenter
```

## Usage
### 1. Create a commandHandler:
```csharp
  var commandHandler = new CommandHandler();
```

### 2. Add Commands:
```csharp
  commandHandler.AddCommand(new CommandBuilder("example")
      .SetDescription("Example command")
      .SetAction(parameters =>
      {
          // Command logic here
          Console.WriteLine("Executing the example command!");
      })
      .Build());
```

### 3. Add Parameters to command:
```csharp
    commandProcessor.AddCommand(new CommandBuilder("dosome")
        .SetDescription("Description")
        .WithParameter("n", "Description for n")
        .SetAction(parameters =>
        {
            string n = parameters.GetParameterValue("n");

            if (n != null)
            {
                DoSomething(n);
            }
            else
            {
                Console.WriteLine("Missing parameters for the 'n' command. Use -n");
            }
        })
        .Build());
```

### 4. Process Commands:
```csharp
  while (true)
  {
      Console.Write("Enter a command: ");
      string input = Console.ReadLine();
      commandHandler.ProcessCommand(input);
  }
```
