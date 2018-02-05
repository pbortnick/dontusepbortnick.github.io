---
layout: post
title:      "Command Line Syntax Checkers"
date:       2018-02-05 16:08:46 -0500
permalink:  syntax_checkers_and_how_to_use_them
---


I have recently started using PHP and learned about the linter tool. Since it worked so well and saved me a bunch of time, I looked into other syntax debugging tools. There are several sites where you can copy and paste your code to check. But with these tools, you can run several files at once. Also, given the human error that might go into copying and pasting, these are potentially more accurate.

**PHP**
1. To check 1 file: * php -l filename.php*
2. To check directory for all php files: *find . -type f -directory_name ".php" -exec php -l {} \; | grep -v 'No syntax errors'*

**Javascript**
1. *npm install lint*
2. To check 1 file: *node-lint path/to/your/file.js*
3. To check directory for all js files: *node-lint directory_name/*

