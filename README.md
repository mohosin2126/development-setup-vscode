
# C/C++ Development Environment Setup in Visual Studio Code Using MinGW

## Overview

This README provides instructions for setting up a C/C++ development environment in Visual Studio Code (VS Code) using the MinGW compiler. Follow the steps below to get started.

## Prerequisites

- **Visual Studio Code**: [Download here](https://code.visualstudio.com/download).
- **MinGW Compiler**: [Download from here](https://drive.google.com/file/d/1DNi19ocKwHWopyYCfTHZGM96puRsGtOQ/view?fbclid=IwAR2ZPt_uPr-w2tmD9CN8I1JiQ3wVs-uwv3Rz9LoA0rljd7Tp0PyM3GjqTwY).

## Installing MinGW

1. **Extract the MinGW Files**: Extract the downloaded MinGW package to a preferred location (e.g., `D:\MinGW`).

2. **Add MinGW to System PATH**:
   - Search for "Environment Variables" in the Start menu.
   - Click on "Edit the system environment variables".
   - In the System Properties window, click on "Environment Variables".
   - In the "System variables" section, find and select the "Path" variable.
   - Click "Edit" → "New", and add the path to the MinGW `bin` folder (e.g., `D:\MinGW\bin`).
   - Click "OK" to close all dialog boxes.

## Configuring Visual Studio Code

1. **Install Required Extensions**:
   - Open VS Code and install the following extensions:
     - **C/C++**
     - **C/C++ Extension Pack**
     - **C/C++ Compile Run**
     - **Code Runner**

2. **Configure `settings.json`**:
   - Open the settings file by going to `File` > `Preferences` > `Settings` and clicking the `{}` icon.
   - Paste the following configuration:

   ```json
   {
       "C_Cpp.default.cppStandard": "c++20",
       "C_Cpp.default.cStandard": "c11",
       "terminal.integrated.defaultProfile.windows": "Git Bash",
       "code-runner.runInTerminal": true,
       "code-runner.saveAllFilesBeforeRun": true,
       "code-runner.terminalRoot": "/",
       "code-runner.executorMapByGlob": {
           "pom.xml": "cd $dir && mvn clean package"
       },
       "code-runner.executorMap": {
           "javascript": "node",
           "java": "cd $dir && javac $fileName && java $fileNameWithoutExt",
           "zig": "zig run",
           "objective-c": "cd $dir && gcc -framework Cocoa $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
           "php": "php",
           "python": "python -u",
           "perl": "perl",
           "perl6": "perl6",
           "ruby": "ruby",
           "go": "go run",
           "lua": "lua",
           "groovy": "groovy",
           "powershell": "powershell -ExecutionPolicy ByPass -File",
           "bat": "cmd /c",
           "shellscript": "bash",
           "fsharp": "fsi",
           "csharp": "scriptcs",
           "vbscript": "cscript //Nologo",
           "typescript": "ts-node",
           "coffeescript": "coffee",
           "scala": "scala",
           "swift": "swift",
           "julia": "julia",
           "crystal": "crystal",
           "ocaml": "ocaml",
           "r": "Rscript",
           "applescript": "osascript",
           "clojure": "lein exec",
           "haxe": "haxe --cwd $dirWithoutTrailingSlash --run $fileNameWithoutExt",
           "rust": "cd $dir && rustc $fileName && $dir$fileNameWithoutExt",
           "racket": "racket",
           "scheme": "csi -script",
           "ahk": "autohotkey",
           "autoit": "autoit3",
           "dart": "dart",
           "pascal": "cd $dir && fpc $fileName && $dir$fileNameWithoutExt",
           "d": "cd $dir && dmd $fileName && $dir$fileNameWithoutExt",
           "haskell": "runghc",
           "nim": "nim compile --verbosity:0 --hints:off --run",
           "lisp": "sbcl --script",
           "kit": "kitc --run",
           "v": "v run",
           "sass": "sass --style expanded",
           "scss": "scss --style expanded",
           "less": "cd $dir && lessc $fileName $fileNameWithoutTrailingSlash.css",
           "FortranFreeForm": "cd $dir && gfortran $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
           "fortran-modern": "cd $dir && gfortran $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
           "fortran_fixed-form": "cd $dir && gfortran $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
           "fortran": "cd $dir && gfortran $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt",
           "sml": "cd $dir && sml $fileName",
           "c": "cd $dir && gcc $fileName -o $fileNameWithoutExt.exe && $dir$fileNameWithoutExt.exe",
           "cpp": "cd $dir && g++ $fileName -o $fileNameWithoutExt.exe && $dir$fileNameWithoutExt.exe"
       },
       "window.zoomLevel": 1,
       "files.autoSave": "afterDelay"
   }
   ```

## Writing Your First Program

Once you have set up your environment, you can write and run your first C or C++ program.

### Example 1: Hello World

Create a new file named `hello.c` and add the following code:

```c
#include<stdio.h>
int main(){
    printf("Hello world!");
    return 0;
}
```

To run the code, press `Ctrl + Alt + N` or use the command palette (`Ctrl + Shift + P`) and type "Run Code".

### Example 2: Input Example

Create another file named `input.c` with the following code:

```c
#include<stdio.h>
int main(){
    int a;
    scanf("%d",&a);
    printf("a = %d",a);
    return 0;
}
```

Run this code using the same method as above.

## Useful Shortcuts

| Operation         | Command    |
|-------------------|------------|
| Copy              | Ctrl + C   |
| Paste             | Ctrl + V   |
| Select All        | Ctrl + A   |
| Open Command Prompt| Win + R, type `cmd`, and press Enter |

## Conclusion

You are now ready to start coding in C and C++. This setup using VS Code and MinGW offers a powerful and flexible development environment. Happy coding!
