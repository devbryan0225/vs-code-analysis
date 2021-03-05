# vs-code-analysis
Based on Pluralsight course : Code Analysis in Visual Studio 2019

# Note
- ruleset will soon be replaced with .editorconfig

## .editorconfig
- dotnet_code_quality:api_surface
- https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/code-quality-rule-options

## code analysis
- remove unneccessary usings
- fix method names
- fix formattings
- highlight a section of the code and make method

## automate with code cleanup tools
- configure profile to add fixers
- per page

## analyze and run code cleanup
- applies to whole solution

## custom rules (not rule sets)
- determine the scope of the analyzer
- options > text editor > C# > code style
- setting preferences to appear with warning or errors
- create .editorconfig file to store in the solutio/ project level.
- anyone working on this solution can get this configuration

## analyzer workflow
- configure
- install
- using roslynator extension as analyzer, not nuget.
- using roslynator as nuget.
- and fxcop analyzer?
- with nuget the warnings shows up in the build.

## rule suppressions
- for certain lines of code
- ex. setting to readonly
- creates assembly file
- modify the file to target type over member etc.
- for all active issues

## writing custom rule sets
- apply to a specific set of code only
- create .ruleset file
- add reference <codeanalysisruleset> in csproj
- update ruleset by selecting the analyzer rule sets under the project
- set to error which will prevent build unless fixed

running from cmd
- dotnet-format
- add to build process


## Build and Deployment Workflow
- Build the application
(write code and setup the Roslyn Analyzers)
- Push Code to Build Server
(Build solution and run quality checks to produce deployable package)
- Deploy to stage environments
(manual stakeholder testing and sign off on new features)
- Deploy to production
(release to end users or customers)

## build pipeline
- doesn't allow build on azure even when checked in without build

## types of code metrics
- cyclomatic complexity
- inheritance depth
- class coupling
- lines of code
- maintainability index

## creating custom analyzer
