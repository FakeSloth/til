# Execute Bash Commands

In Ruby, there are a few different ways of making a program execute shell commands. Here are two of them:
```ruby
`echo "Hello world"`
```
or
```ruby
Kernel.system "echo 'Hello world'"
```

The first of the two will run the command silently (the user won't see it). This is useful if you want to create a variable that is equivalent to the output of a command (e.g. "uname -a") and don't want the user to be able to see what is being run.

The second will show the output of the given command and it doesn't appear as though you can set the output equal to a variable. This is useful for changing aspects of the user's computer such as installing packages required for later bash commands (e.g. insuring that something like curl or wget is installed as they are not always bundled with Linux distros).
