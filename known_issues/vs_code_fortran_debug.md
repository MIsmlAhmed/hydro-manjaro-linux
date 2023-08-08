# Configure vs code to work with fortran debugging
1. Install the following extensions: `Modern Fortran`, `Fortran Breakpoint Support`, `C/C++`, `Makefile Tools`, `GDB Debugger - Beyond`
2. Make sure that your makefile has the `-g` flag and remove the `-o` flag because it limits the info for debugging
3. In your working directory (from the vs code file browser), create a new folder `.vscode`
4. In the `.vscode` folder, create a `tasks.json` file that contains the following script, which is used to run a make command and generate the exe to debug
`````
{
    "version": "2.0.0",
    "tasks":[
    {
            "label":"make",
            "type": "shell",
            "command": "make",
            "options": {
                "cwd": "${workspaceFolder}"
            }
        }
    ]
}
`````
4. In the `.vscode` folder, create a `launch.json` that contains the following script, which is used to run the debugger:
`````
{
        "version": "0.2.0",
        "configurations": [
        {
        "name": "Run GDB", 
        "type": "cppdbg",
        "request": "launch",
        "program": "${workspaceFolder}/your_exe_name",
        "args": [],
        "stopAtEntry": false,
        "cwd": "${workspaceFolder}",
        "externalConsole": false,
        "MIMode": "gdb",
        "preLaunchTask": "make",
        }
    ]
}
`````
5. set a breakpoint and press `F5` to start debugging

So far, there is a problem in displaying arrays but working on fixing that.
