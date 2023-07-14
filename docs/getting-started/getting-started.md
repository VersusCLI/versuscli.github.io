---
layout: default
title: Getting Started
has_children: true
nav_order: 3
---

# Getting Started
To get started with Versus cli you can run the
```
versus init
```
Command to initialize a project containing all the directories and files needed.

Once Initialized you should have a filesystem looking like this:
```
:root
  > src
    > main
      > javascript (main code)
      > resources
      
    > test
      > javascript (test code)
      > resources (test resources)

  - versus.config.json (Versus config)
  - package.json (npm packager config)
```
**Note:** That this may change within the versions like folders getting added or files getting removed etc.

We can now continue to the `versus.config.json` file, it should look like this:
```json
{
    "$VERSION": "VERSUS VERSION DO NOT CHANGE",
    "name": "Project Name (Must be all lowercase without spaces)",
    "version": "Project version",
    "description": "Project Description",
    "license": "License (Default: MIT)",
    "main": "Javascript Main file (Default: com.example.Main)"
}
```
This is what the config will look like when you initialize the project.  
You can change anything here besides the $VERSION field.  
The $VERSION field is used in the cli itself to check if the current version of versus is allowed to be used with the current project.

We can check out the main field which gonna point out to a file without the extension. (Example: net.mydevelopment.project.MainFile)

## Adding files / resources
To add files or resources you will need to follow these rules:
- Make sure the files (javascript / typescript) created in the javascript folder.
- Resources should be in the resources folder

When using jsar packaging It's gonna take these files:
```
> Source Directory Files (/src/main/javascript)
> Resource Directory Files (/src/main/resources)
> versus.config.json
```
If any other files not inside these two folders (resources, javascript folder) then it wont be built into the jar file.