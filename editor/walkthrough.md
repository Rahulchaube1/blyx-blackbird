## Resolve both occurrences of an ambiguous wall time

Returns [candidate count, selected UTC, selected offset]. For a gap the latter two values are zero. Fold 0 chooses the earlier occurrence and fold 1 the later. Supply transition data from a trusted timezone database. Invalid arguments and nonfinite results return an empty vector.

1. Open an empty file named `blackbird-demo.blyx`.
2. Type `blyx-blackbird-demo` and select **Blackbird — runnable example**. You can also use **Snippets: Fill File with Snippet**.
3. Choose **Blyx: Run File** from the command palette. Change an argument near the end of `fn main()` to try another input.

Expected output

```text
2
11000
0
```

[Work through the example in the browser](https://www.blyx-lang.space/play?example=package-blackbird)
