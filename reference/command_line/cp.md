### cp

The `cp` command copies a files from one container to another or between a container and the native filesystem. 

```
Usage: spoon cp [<source-container>:]<path-from> [<target-container>:]<path-to>

<options> available:
     --format=VALUE         Use json format for output
```

#### Examples:

```
# Copy a file from a container to the native system
> spoon cp 2de7:C:\project\file.txt C:\Users\Spoonuser

# Copy a file from a container to another container
> spoon cp 2de7:C:\project\file.txt 3vj3:C:\other-project

# Container paths must be absolute
> spoon cp 2de7:file.txt C:\Users\Spoonuser

ERROR

# Native paths are relative to the current prompt
C:\Users> spoon cp 2de7:C:\project\file.txt \Spoonuser
```

#### JSON output

When `--format=json` option was passed this command will provide output in JSON format. It will contain only an exit code data or an `error` object if command failed.