# Blyx Blackbird

Resolve a wall-clock timestamp at a known gap or fold without guessing its offset.

This extension includes the Blyx Blackbird 0.1.0 source, a runnable example and completions for its public functions. It uses the Blyx Language extension for syntax highlighting and execution.

## Run in the editor

1. Open an empty file named `blackbird-demo.blyx`.
2. Type `blyx-blackbird-demo` and select **Blackbird — runnable example**. You can also use **Snippets: Fill File with Snippet**.
3. Choose **Blyx: Run File** from the command palette. Change an argument near the end of `fn main()` to try another input.

Expected output

```text
2
11000
0
```

## Use Blackbird in a project

Extract the starter into a new folder. It contains `main.blyx`, the licensed framework source in `vendor/blackbird`, and a VS Code task. With the Blyx 0.2.1 compiler and host toolchain installed, run `blyxc native-run main.blyx` from that folder. Type `blyx-blackbird-` in a Blyx file to see the framework completions. [Download the starter ZIP](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-blackbird-starter-0.1.0.zip)

[API and input requirements](https://www.blyx-lang.space/packages/blackbird) · [Framework source](https://github.com/Rahulchaube1/blyx-blackbird/tree/30dc8057641e7f2b2d2715cdb5a666304f50571e) · [Report an issue](https://github.com/Rahulchaube1/blyx-blackbird/issues)

[GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) · [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube)
