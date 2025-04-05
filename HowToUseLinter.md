# How to use linter?

- [How to use linter?](#how-to-use-linter)
  - [What is linter?](#what-is-linter)
  - [What are the benefits of using linter?](#what-are-the-benefits-of-using-linter)
  - [Common linter tools](#common-linter-tools)
  - [Clang-Format (C/C++)](#clang-format-cc)
    - [1. Install Clang-Format](#1-install-clang-format)
    - [2. Configure Clang-Format](#2-configure-clang-format)
    - [3. Format Code](#3-format-code)
    - [Example](#example)
    - [.clang-format Template](#clang-format-template)
  - [Black (Python)](#black-python)

## What is linter?

Linter is a tool that automatically maintains consistent coding style and ensures adherence to coding standards.

> The name "lint" originates from a tool created by Stephen C. Johnson at Bell Labs in 1978. Just as a clothes dryer's lint trap catches unwanted fibers, a code linter catches problematic code patterns without affecting the core functionality.

## What are the benefits of using linter?

- Enforce a unified project code style to improve code readability.
- Save time and effort in manually adjusting layout through automated processes.
- No need to spend time discussing coding style during code review.
- Through the file configuration rules in a specific format, these configuration files can also be version controlled together with the code.

## Common linter tools

C/C++:
- Clang-Format
- PC-lint

Python:
- Pylint
- Flake8
- Black

## Clang-Format (C/C++)

- Clang-Format is a tool from LLVM project that formats C/C++ code.
- It can be used to format code according to a style configuration file called `.clang-format`.

### 1. Install Clang-Format

- (Windows) Download the pre-build installer from [LLVM website](https://llvm.org/builds/).
- (Linux) Install from `sudo apt-get install clang-format`.
- (macOS) Install from `brew install clang-format`.
- You can run `clang-format --version` to check if the installation is successful.

### 2. Configure Clang-Format

- Create a `.clang-format` file in the root directory of your project.
- You can also run `clang-format -style=llvm -dump-config > .clang-format` to dump the default style configuration and then modify it.
- You can use the [Clang-Format Style Options](https://clang.llvm.org/docs/ClangFormatStyleOptions.html) to configure the style.

### 3. Format Code

- To format a single file, run `clang-format -i <file_name>`.
- In VSCode, you can install the `Clang-Format` extension to format code by right-clicking on the code and selecting `Format Document`(or the shortcut `Ctrl+Shift+F`).

### Example

```cpp
#include <stdio.h>
#include<stdlib.h>
#define MAX 100

int main() {
int arr[MAX];
int n,i,j,temp;
printf("Enter the number of elements: ");
scanf("%d",&n);
printf("Enter %d integers:\n",n);
for(i=0;i<n;i++){scanf("%d",&arr[i]);}
for(i=0;i<n-1;i++){
for(j=0;j<n-i-1;j++){
if(arr[j]>arr[j+1]){
temp=arr[j];
arr[j]=arr[j+1];
arr[j+1]=temp;
}
}
}
printf("Sorted array in ascending order:\n");
for(i=0;i<n;i++){printf("%d ",arr[i]);}
return 0;
}
```

After formatting, the code will be:

```cpp
#include <stdio.h>
#include <stdlib.h>
#define MAX 100

int main()
{
    int arr[MAX];
    int n, i, j, temp;
    printf("Enter the number of elements: ");
    scanf("%d", &n);
    printf("Enter %d integers:\n", n);
    for (i = 0; i < n; i++)
    {
        scanf("%d", &arr[i]);
    }
    for (i = 0; i < n - 1; i++)
    {
        for (j = 0; j < n - i - 1; j++)
        {
            if (arr[j] > arr[j + 1])
            {
                temp       = arr[j];
                arr[j]     = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
    printf("Sorted array in ascending order:\n");
    for (i = 0; i < n; i++)
    {
        printf("%d ", arr[i]);
    }
    return 0;
}
```

### .clang-format Template

Source: [google-style-clang-format](https://github.com/kehanXue/google-style-clang-format)

```yaml
# Google C/C++ Code Style settings
# https://clang.llvm.org/docs/ClangFormatStyleOptions.html
# Author: Kehan Xue, kehan.xue (at) gmail.com

Language: Cpp
BasedOnStyle: Google
AccessModifierOffset: -1
AlignAfterOpenBracket: Align
AlignConsecutiveAssignments: None
AlignOperands: Align
AllowAllArgumentsOnNextLine: true
AllowAllConstructorInitializersOnNextLine: true
AllowAllParametersOfDeclarationOnNextLine: false
AllowShortBlocksOnASingleLine: Empty
AllowShortCaseLabelsOnASingleLine: false
AllowShortFunctionsOnASingleLine: Inline
AllowShortIfStatementsOnASingleLine: Never  # To avoid conflict, set this "Never" and each "if statement" should include brace when coding
AllowShortLambdasOnASingleLine: Inline
AllowShortLoopsOnASingleLine: false
AlwaysBreakAfterReturnType: None
AlwaysBreakTemplateDeclarations: Yes
BinPackArguments: true
BreakBeforeBraces: Custom
BraceWrapping:
  AfterCaseLabel: false
  AfterClass: false
  AfterStruct: false
  AfterControlStatement: Never
  AfterEnum: false
  AfterFunction: false
  AfterNamespace: false
  AfterUnion: false
  AfterExternBlock: false
  BeforeCatch: false
  BeforeElse: false
  BeforeLambdaBody: false
  IndentBraces: false
  SplitEmptyFunction: false
  SplitEmptyRecord: false
  SplitEmptyNamespace: false
BreakBeforeBinaryOperators: None
BreakBeforeTernaryOperators: true
BreakConstructorInitializers: BeforeColon
BreakInheritanceList: BeforeColon
ColumnLimit: 80
CompactNamespaces: false
ContinuationIndentWidth: 4
Cpp11BracedListStyle: true
DerivePointerAlignment: false  # Make sure the * or & align on the left
EmptyLineBeforeAccessModifier: LogicalBlock
FixNamespaceComments: true
IncludeBlocks: Preserve
IndentCaseLabels: true
IndentPPDirectives: None
IndentWidth: 4
KeepEmptyLinesAtTheStartOfBlocks: true
MaxEmptyLinesToKeep: 1
NamespaceIndentation: None
ObjCSpaceAfterProperty: false
ObjCSpaceBeforeProtocolList: true
PointerAlignment: Left
ReflowComments: false
SeparateDefinitionBlocks: Always   # Only support since clang-format 14
SpaceAfterCStyleCast: false
SpaceAfterLogicalNot: false
SpaceAfterTemplateKeyword: true
SpaceBeforeAssignmentOperators: true
SpaceBeforeCpp11BracedList: false
SpaceBeforeCtorInitializerColon: true
SpaceBeforeInheritanceColon: true
SpaceBeforeParens: ControlStatements
SpaceBeforeRangeBasedForLoopColon: true
SpaceBeforeSquareBrackets: false
SpaceInEmptyParentheses: false
SpacesBeforeTrailingComments: 2
SpacesInAngles: false
SpacesInCStyleCastParentheses: false
SpacesInContainerLiterals: false
SpacesInParentheses: false
SpacesInSquareBrackets: false
Standard: c++11
TabWidth: 4
UseTab: Never
```

## Black (Python)

Refer to [Black](https://github.com/psf/black) for more information.
