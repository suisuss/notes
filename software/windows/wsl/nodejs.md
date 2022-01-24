### NodeJS

#### Installation

`sudo apt install nodejs npm`

#### Problems

**`npm install` results in error `/usr/bin/env: ‘bash\r’: No such file or directory`:**

- This is a line endings issue.
  - Fix it by creating/editing /etc/wsl.conf with `sudo nano /etc/wsl.conf`.
    - Add `[interop]\n appendWindowsPath = false`.

