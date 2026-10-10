# Sea Port Simulation - VS Code Run Guide (Mac)

This project is a C++ OpenGL/GLFW app. It was adjusted to be more portable for Mac and VS Code usage.

## 1) Install required tools on Mac

Open Terminal and run:

```bash
xcode-select --install
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Then install the required libraries:

```bash
brew install glfw glm
```

If you do not have CMake or compiler tools already, make sure Apple Clang is available from Xcode Command Line Tools.

## 2) Open the project in VS Code

Open the folder:

```text
GraphicsProject-main-main
```

Make sure the project root is the workspace folder.

## 3) Build the project

In VS Code Terminal:

```bash
cd "path/to/GraphicsProject-main-main"
make
```

If you want to clean and rebuild:

```bash
make clean && make
```

This will produce the binary:

```text
app
```

## 4) Run the app

From Terminal:

```bash
./app
```

Or use VS Code Run and Debug:

- Open Run and Debug panel
- Select: `Run Sea Port Simulator`
- Press `F5`

The project already includes the VS Code launch config in `.vscode/launch.json`.

## 5) If the app does not open

Check that the working directory is the project root.

Also verify the binary exists:

```bash
ls -l app
```

If it is missing, run:

```bash
make
```

## 6) Important Mac note

This project is an OpenGL application, so it needs a graphical desktop session. It will not run properly in a pure terminal-only environment.

Use a normal Mac desktop environment or VS Code opened on the Mac desktop, not inside a remote/headless terminal session.

## 7) Useful commands

```bash
make
./app
make clean
```

## 8) Troubleshooting

### `GLFW initialization failed.`
Possible reasons:
- no desktop session on the Mac
- missing Xcode command line tools
- GLFW not installed

Fix:

```bash
xcode-select --install
brew install glfw glm
```

### `shader file not found`
The project has been updated to resolve shader paths more safely, but always run the app from the project root.

### Build fails
Try:

```bash
make clean
make
```

## 9) Recommended workflow for your Mac

1. Open project in VS Code
2. Open integrated terminal
3. Run `make`
4. Press `F5` or run `./app`

If everything is correct, the 3D sea port simulation should launch in a normal desktop window.
