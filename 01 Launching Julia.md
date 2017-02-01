# Launching Julia
## Cloud9
Create an account on [C9](https://c9.io/). Then:

- `Create a new workspace`
- Random name and optional description
- `Choose a template` Blank
- `Create workspace`

Once the workspace is finished initializing, locate a terminal (`Alt+T`) and paste each line, pressing the Enter key and following the instructions on-screen after each paste:

```
sudo add-apt-repository ppa:staticfloat/juliareleases
sudo add-apt-repository ppa:staticfloat/julia-deps
sudo apt-get update
sudo apt-get install libgmp3-dev julia
```

After, you can run any file ending in `.jl` using Julia, or use the REPL by typing `julia` in a terminal.

## JuliaBox
Click the Terminal tab. You now have a Bash terminal to use. To launch the Julia REPL, simply type `julia` in the prompt. Exit the REPL using `exit()`.
## Local
Simply launch the Julia installation for a REPL. Same thing as JuliaBox, but done locally.
