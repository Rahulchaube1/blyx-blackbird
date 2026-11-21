<img src="assets/logo.png" width="112" height="112" alt="A charcoal blackbird tilts its head, showing an orange eye ring and bill.">

# Blackbird

Resolve a wall-clock timestamp at a known gap or fold without guessing its offset. This Blyx workflow framework is part of the calendar, scheduling and local time collection.

One wall time can occur twice during a fall-back transition and disappear entirely during a forward jump. Expose the number of valid UTC candidates. [PEP 495, local time disambiguation](https://peps.python.org/pep-0495/)

## Editor extension

Install **RahulChaube.blyx-blackbird** to run the worked example and use the framework’s function completions in a Blyx file. Open an empty `.blyx` file, enter `blyx-blackbird-demo`, then choose **Blyx: Run File**. [Editor downloads](https://www.blyx-lang.space/packages/blackbird#editor) · [Download the extension](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-blackbird-0.1.0.vsix) · [Starter with framework source](https://github.com/Rahulchaube1/blyxxxx/releases/download/framework-editors-v0.1.0/blyx-blackbird-starter-0.1.0.zip)

## Install and run

Install [Blyx 0.2.1](https://www.blyx-lang.space/download) with a Rust toolchain and host linker for native builds.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-blackbird.git
cd blyx-blackbird
blyxc native-run example.blyx
blyxc native-run tests.blyx
```

[Run the editable browser example](https://www.blyx-lang.space/play?example=package-blackbird) · [Package page](https://www.blyx-lang.space/packages/blackbird) · [Handbook](https://doc.blyx-lang.space/guide/blackbird)

## Import the module

Run this in the directory containing your application's entry file.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-blackbird.git vendor/blackbird
```

```blyx
use vendor::blackbird::blackbird;

fn main() {
    let local = 11000.0;
    let transition = 10000.0;
    let before = 3600.0;
    let after = 0.0;
    let fold = 1.0;
    let result = blackbird_resolve(local, transition, before, after, fold);
    if len(result) == 0 { println!("invalid"); return; }
    let mut i = 0;
    while i < len(result) {
        println!(at(result, i));
        i += 1;
    }
}
```

Expected output

```text
2
11000
0
```

## API

`blackbird_resolve(local, transition, before, after, fold)`

Returns [candidate count, selected UTC, selected offset]. For a gap the latter two values are zero. Fold 0 chooses the earlier occurrence and fold 1 the later. Supply transition data from a trusted timezone database. Invalid arguments and nonfinite results return an empty vector. Integers carried in numeric vectors use the exact range from −(2^53−1) to 2^53−1.

| Argument | Domain |
| --- | --- |
| local | A exact signed integer |
| transition | A exact signed integer |
| before | A exact signed integer |
| after | A exact signed integer |
| fold | A nonnegative exact integer |

## Run the command-line project

Run the example with your own numbers. Vector arguments accept up to 16 comma-separated entries; use `[]` for an empty vector. The imported API accepts longer vectors. Invalid arguments return a nonzero exit status.

```sh
blyxc native-run project.blyx -- 11000 10000 3600 0 1
```

## Libraries

- [CivilOffset](https://github.com/Rahulchaube1/blyx-civiloffset/tree/v0.1.0) — Convert a local tick to a candidate UTC tick for a supplied offset.
- [ClockFold](https://github.com/Rahulchaube1/blyx-clockfold/tree/v0.1.0) — Classify a local time around one supplied offset transition.

This release includes identical copies of both library modules so a tagged clone can build offline.

## Verification and contributions

The regression suite in [tests.blyx](tests.blyx) checks the example, boundary cases and invalid inputs. Include a short reproducer and your compiler version in [an issue](https://github.com/Rahulchaube1/blyx-blackbird/issues). The source is dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE). The [artwork notice](assets/NOTICE.txt) records credits for earlier editions.

## Connect with Rahul Chaube

[Portfolio](https://www.rahulchaube1.com/) · [GitHub](https://github.com/Rahulchaube1) · [LinkedIn](https://www.linkedin.com/in/rahulchaube1) · [Hugging Face](https://huggingface.co/oncody) · [X](https://x.com/RahulChaube_) · [EverestQ](https://www.everestqai.com/) · [Contact](https://www.rahulchaube1.com/contact)

[Blyx website](https://www.blyx-lang.space/) · [BlyxTorch](https://www.blyx-lang.space/packages/blyxtorch) · [Handbook](https://doc.blyx-lang.space/) · [Community](https://www.blyx-lang.space/community)

Support Rahul’s open-source work through [GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) or [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube).
