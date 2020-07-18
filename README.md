# How to Debug Bash with VS Code

## Summary

- [Basic](#basic)
- [Spec](#spec)
- [Instruction](#instruction)
- [debugging executable file](#debugging-executable-file)

## Basic

- [GNU Bash](https://www.gnu.org/software/bash/)
- Extension: [Bash Debug](https://marketplace.visualstudio.com/items?itemName=rogalmic.bash-debug)
- Debugger: [bashdb](http://bashdb.sourceforge.net/)
- module code: [bubble_sort.sh](https://github.com/74th/vscode-debug-specs/blob/master/bash/bubbleSort.sh)

## Spec

- OS
  _ ✅ MacOS
  _ ✅ Windows \* ✅ Linux
- Break Point
  _ ✅ break point
  _ ❌ condition break point : able to set, but not working \* ❌ function breakpoint
- Step Execution
  _ ✅ Step Over
  _ ✅ Step Into
  _ ✅ Step Out
  _ ✅ Continue
  _ ❌ Step Back
  _ ❌ Move To \* ❌ Pause
- Variables
  _ ✅ variables views
  _ ✅ watch variables
- Call Stack \* ✅ call stack
- Evaluation
  _ ✅ eval expression to show variables
  _ ✅ eval expression to change variables
- Type of Execution
  _ ✅ debug executable package
  _ ❌ remote debugging

## Instruction

### MacOS

```
brew install bashdb
```

### Linux(Ubuntu 18.04)

Ubuntu 18.04 don't have bashdb package. You need build from source.

see https://github.com/rogalmic/vscode-bash-debug/issues/67

### Windows

- [install wsl Ubuntu18.04](https://www.microsoft.com/store/productId/9N9TNGVNDL3Q)
- see Linux instruction

## debugging executable file

- Program: [bubble_sort.sh](https://github.com/74th/vscode-debug-specs/blob/master/bash/bubbleSort.sh)

### launch.json

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Bash-Debug (hardcoded script name)",
      "type": "bashdb",
      "request": "launch",
      "program": "${workspaceRoot}/bubbleSort.sh",
      "commandLineArguments": "4 3 2 1"
    }
  ]
}
```
