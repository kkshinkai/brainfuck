Brainfuck
=========

> **WIP**

This is a small demo for testing the C++ environment configuration on macOS,
using VSCode, CMake, LLVM, Clang, Clang Format, Clangd, Clang Tidy and LLDB.

Dependencies
------------

**Clang ≥ 12.0.0** and **CMake ≥ 3.20**

<details><summary><strong>Install LLVM 12.0.0 with Clang</strong></summary>

-   **Install LLVM 12.0.0 with Clang**, they are available on the GitHub release
    [page]. Add it to your path. For example, under macOS, if you put the
    downloaded directory in the `~` directory, you can use the following
    commands (don't forget `source ~/.zshrc` after that):

    ```shell
    echo 'export PATH="$HOME/clang+llvm-12.0.0-x86_64-apple-darwin/bin:$PATH"' >> ~/.zshrc
    ```

[page]: https://github.com/llvm/llvm-project/releases/tag/llvmorg-12.0.0

-   (macOS Only) Verify all executable files under that directory, this may
    require password.

    ```shell
    sudo xattr -dr com.apple.quarantine `find $HOME/clang+llvm-12.0.0-x86_64-apple-darwin/bin`
    ```

-   (macOS Only) Setup `SDKROOT` correctly, pay special attention to the
    version number.

    ```shell
     export SDKROOT="/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX11.3.sdk"
    ```

-   **Now we have `clang++`, `clang-format`, `clang-tidy`, `clangd` and `lldb`.**

    ```shell
    clang++ --version        
    # clang version 12.0.0
    # Target: x86_64-apple-darwin20.3.0
    # Thread model: posix
    # InstalledDir: /Users/kkshinkai/clang+llvm-12.0.0-x86_64-apple-darwin/bin
    ```

-   **Build and run.**

    ```shell
    # Use GNU Makefile
    cmake -B build .
    make -C build

    # Use Ninja
    cmake -B build -G Ninja .
    ninja -C build

    # Run
    ./build/bf
    ```

</details>

<details><summary><strong>Install VSCode and it's extensions</strong></summary>

-   **Download and install Visual Studio Code (VSCode)** from [here].

[here]: https://code.visualstudio.com

-   **Download the following extensions**

Name: C/C++
Id: ms-vscode.cpptools
Description: C/C++ IntelliSense, debugging, and code browsing.
Version: 1.5.1
Publisher: Microsoft
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools

Name: CMake Tools
Id: ms-vscode.cmake-tools
Description: Extended CMake support in Visual Studio Code
Version: 1.7.3
Publisher: Microsoft
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=ms-vscode.cmake-tools

Name: clangd
Id: llvm-vs-code-extensions.vscode-clangd
Description: C and C++ completion, navigation, and insights
Version: 0.1.12
Publisher: LLVM Extensions
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=llvm-vs-code-extensions.vscode-clangd

Name: Clang-Tidy
Id: notskm.clang-tidy
Description: Integrates clang-tidy into VS Code
Version: 0.5.1
Publisher: notskm
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=notskm.clang-tidy

</details>