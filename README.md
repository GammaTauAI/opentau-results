# Repository with the results from OpenTau

Link to the main repository: https://github.com/GammaTauAI/opentau

## Results table

| Config                                         | Percent Typecheck   | Avg Heuristic | Avg errors |
| ---------------------------------------------- | ------------------- | ------------- | ---------- |
| Santacoder TS FT - Baseline - 2048             | 245/744 (32.9%)     | 200.7         | 4.7        |
| Santacoder FIT FT - Baseline - 2048            | 297/744 (39.9%)     | 200.9         | 5.2        |
| Incoder - Baseline - 2048                      | TODO                | TODO          | TODO       |
| Santacoder FIT FT - Baseline - 1024            | 248/744 (33.3%)     | 200.7         | 5.1        |
| Santacoder FIT FT - Baseline - 512             | 178/744 (23.9%)     | 201.2         | 6.3        |
| Santacoder FIT FT - Tree with usages - 2048    | **353/744 (47.4%)** | **154.6**     | **3.3**    |
| Santacoder FIT FT - Tree without usages - 2048 | 274/744 (36.8%)     | 168.4         | 3.7        |

#### Notes about the results

- Metrics in **bold** are the best results for each column.
- FIT FT means that the model was fine-tuned for _Fill-In-the-Type_, for more
  information about the technique, please refer to the repository: https://github.com/GammaTauAI/santacoder-finetuning
- TS FT means that the model was fine-tuned for TypeScript code generation, **NOT** for _Fill-In-the-Type_ (FIT)
  or Fill-In-the-Middle (FIM).
- The numbers at the end (e.g. 2048, 1024, 512) are the maximum number of characters for the context window
  when running inference with the model.
