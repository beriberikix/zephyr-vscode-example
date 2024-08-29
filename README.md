# zephyr-vscode-example

This is an example configuration for setting up Visual Studio Code for Zephyr application development. It was originally created for the talk entitled, "[Zephyr & Visual Studio Code: How to Develop Zephyr Apps with a Modern, Visual IDE](https://youtu.be/IKNHPmG-Qxo)" at EOSS 2023.

## Example details

There are many, many different ways to develop a Zephyr application. This example currently assumes:

* All paths follow the Getting Started Guide
* Uses the Zephyr SDK where possible (ex. Host tools are not available on macOS or Windows)
* In-tree development
* Use of Python Virtual Environments
* Building `samples/basic/thread` so we can demonstrate thread-aware debugging
* Targetting an nRF52840 DK 

## Steps

1. Follow the Zephyr [Getting Started Guide](https://docs.zephyrproject.org/latest/develop/getting_started/index.html) for your OS and make sure to use virtual environments
2. Go to your workspace directory `cd ~/zephyrproject`
3. Turn on Compilation Database with `west config build.cmake-args -- -DCMAKE_EXPORT_COMPILE_COMMANDS=ON`
4. Copy the `.code-workspace` for your OS to `samples/basic/thread` as well the `.vscode` folder
5. Retrieve `ZEPHYR_SDK_INSTALL_DIR` with `cmake -P zephyr/cmake/verify-toolchain.cmake`. It'll be the prefix of the `C_Cpp.default.compilerPath`
6. Set the `Python: Interpreter Path`
7. CD to `samples/basic/thread`
8. Try the different build tasks and the flash task
9. Try to connect over the serial terminal
10. TODO try step debugging

## Credits

https://zmk.dev/docs/development/ide-integration
