# Repository with the results from OpenTau

Link to the main repository: https://github.com/GammaTauAI/opentau

Link to the dataset used for evaluation: https://huggingface.co/datasets/nuprl/ts-eval

## 744-dataset Results table

| Configuration                              | Percent Typecheck   | Avg Heuristic | Avg type errors |
| ------------------------------------------ | ------------------- | ------------- | --------------- |
| Santacoder TS FT - Baseline - 2048         | 245/744 (32.9%)     | 200.7         | 4.7             |
| Santacoder FIT FT - Baseline - 2048        | 297/744 (39.9%)     | 200.9         | 5.2             |
| Santacoder FIT FT - Baseline - 1024        | 248/744 (33.3%)     | 200.7         | 5.1             |
| Santacoder FIT FT - Baseline - 512         | 178/744 (23.9%)     | 201.2         | 6.3             |
| Santacoder FIT FT - Tree, no usages - 2048 | 274/744 (36.8%)     | 168.4         | 3.7             |
| Santacoder FIT FT - Tree, usages - 2048    | **353/744 (47.4%)** | **154.6**     | **3.3**         |

### Configuration to file mapping

| Configuration                       | File name in the repository                           |
| ----------------------------------- | ----------------------------------------------------- |
| Santacoder TS FT - Baseline - 2048  | `santacoder_baseline_finetuned_ts_ts-eval.json`       |
| Santacoder FIT FT - Baseline - 2048 | `santacoder_baseline_finetuned_fim_2048_ts-eval.json` |
| Santacoder FIT FT - Baseline - 1024 | `santacoder_baseline_finetuned_fim_1024_ts-eval.json` |
| Santacoder FIT FT - Baseline - 512  | `santacoder_baseline_finetuned_fim_512_ts-eval.json`  |
| Santacoder FIT FT - Tree, no usages | `santacoder_tree_nousages_ts-eval.json`               |
| Santacoder FIT FT - Tree, usages    | `santacoder_tree_ts-eval.json`                        |

#### Notes about the results

- Metrics in **bold** are the best results for each column.
- All rows for the 744 runs had 0 average syntax errors, thus we did not include the column in the table.
- FIT FT means that the model was fine-tuned for _Fill-In-the-Type_, for more
  information about the technique, please refer to the repository: https://github.com/GammaTauAI/santacoder-finetuning
- TS FT means that the model was fine-tuned for TypeScript code generation, **NOT** for _Fill-In-the-Type_ (FIT)
  or Fill-In-the-Middle (FIM).
- The numbers at the end (e.g. 2048, 1024, 512) are the maximum number of characters for the context window
  when running inference with the model.

## 50-dataset Results table (Parser Disabled)

**Both rows used the Baseline and the maximum context window size was 2048 characters.**

| Configuration     | Percent Typecheck | Avg Heuristic | Avg type errors | Avg syntax errors |
| ----------------- | ----------------- | ------------- | --------------- | ----------------- |
| Santacoder TS FT  | 1/50 (2.0%)       | 0             | 121.2           | 42.1              |
| Santacoder FIT FT | 25/50 (50.0%)     | 230.0         | 4.6             | 0.2               |

### Configuration to file mapping

| Configuration     | File name in the repository                                      |
| ----------------- | ---------------------------------------------------------------- |
| Santacoder TS FT  | `santacoder_baseline_noparser_normal_ts-eval-subset.json`        |
| Santacoder FIT FT | `santacoder_baseline_noparser_fim_finetuned_ts-eval-subset.json` |
