# <%= repo %> 

> This is a short description of your project. It should be short, concise and easy to understand.

## Table of Contents

* [Installation](#installation)
* [Usage](#usage)
* [Options](#options)
* [Example](#example)
* [Example Output](#example-output)
* [Building and Testing](#building-and-testing)
* [Contributing](#contributing)
* [Legal](#legal)
* [Release History](#release-history)

## Installation
[[Back To Top]](#table-of-contents)

- via npm

```shell
npm install <%= repo %>
```

- Manually

```shell
git clone git://github.com/<%= user %>/<%= repo %>.git
```

## Usage
[[Back To Top]](#table-of-contents)

```javascript
var <%= repo %> = require('<%= repo %>');
<%= repo %>.awesome(); // "awesome"
```

If the output's line is more than the maximum bytes, then the rest of the characters will be treated as if it's in the next line. Meaning that you can find a very long line split into two in the `output` array key. Right now the max char limit is `16384` bytes.


## Options
[[Back To Top]](#table-of-contents)

- `chained`: `bool`

  `chained`, which is `true` by default, is an option that can stop running commands after one of them failed. To see if it failed, it checks the exit code of the command that is run.

- `returnOutput`: `bool`

  `returnOutput` is also `true` by default. This is what returns the output in an array, parsing them line by line. I supply with this option because sometimes you might run a command that only returns server's IP address or sometimes you can run a command that just outputs very long lines and a very long text. I added the ability to opt out so that when unnecessary you might set it to false.

## Example
[[Back To Top]](#table-of-contents)

```js
//require the extension/module/wtv
var execxi = require("execxi");

// I just defined some commands here
// These will run for a long time. So you can see that outputs are occurring in real-time.
var long_commands = ["find ~/"];
// These are just some shell scripts that exit with different exit codes
// one exits with 0, other exists with 1, and lastly 2.
var exit_codes = ["./tests/exit_0.sh","./tests/exit_1.sh","./tests/exit_2.sh"];
// this is non existent command to see what happens when it doesn't find the command to run.
// returns 127 exit code.
var non_existent = ["./tests/sadf.sh"];
// this is just a command that echoes one line, 5000 bytes.
var long_text = ["./tests/echo_bytes_5000.sh"];
// some regular commands that run successfully
var regular = Array("ls","echo \"Works\"", "ls -lart");


```

## Example Output
[[Back To Top]](#table-of-contents)

That example outputs something long like this:

```
Some Output
Coming Soon
```


## Building and Testing
[[Back To Top]](#table-of-contents)

I have packaged a `Makefile`, `Gruntfile` for building and testing, and `npm` scripts point to those.

Available commands are:

- `make` (Aliases: `npm run-script preinstall`) : 
  Compiles the C++ code into node extension.

- `make clean` (Aliases: `npm run-script preuninstall`):
  Removes the `build` directory.

- `node test` (Aliases: `make test`) : 
  This is for visual testing rather than unit testing. 

- `grunt test`  (Aliases: `grunt`; `npm test`): 
  This is for unit testing. 

## Legal
[[Back To Top]](#table-of-contents)

Copyright Â© <%= year %> <%= user %> <aponxi@weaponxi.com>

This software is licensed under [<%= license %>](/LICENSE.txt).

## Release History
[[Back To Top]](#table-of-contents)

You can find [all the changelogs here](/CHANGELOGS.md).
