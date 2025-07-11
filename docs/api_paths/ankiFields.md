# `ankiFields`

Returns rendered Anki handlebars for dictionary entries found for search text.

## Request Options

- Request method: `POST`

- Body:

    - `text` (`string`): Contains the text to search for.

    - `type` (`string`): The type of dictionary to search in: `term` or `kanji`.

    - `markers` (`array<string>`): The markers (often called handlebars) to return. Do not include handlebars brackets (`{}`).

        A list of available handlebars can be found in Rikaitan's settings. Open the settings, navigate to the `Anki` category, open `Configure Anki flashcards…`, and click `Help`.

        The Rikaitan Wiki also has a list on the [Anki page](https://rikaitan.github.io/anki/) under `Markers for Term Cards` or `Markers for Kanji Cards`.

    - `maxEntries` (`int`): The number of search entries to render markers for.

## Request Example

- Request method: `POST`

- Body:
    ```json
    {
        "text": "わかる",
        "type": "term",
        "markers": ["expression", "glossary"],
        "maxEntries": 2
    }
    ```

## Response Example (200)

Glossary has been truncated in this example.

```json
[
    {
        "expression": "分かる",
        "glossary": "<div style=\"text-align: left;\" class=\"rikaitan-glossary\"><i>(priority form, ★, jmdict.org [2025-05-13])</i> <span><ul style=\"list-style-type:&quot;＊&quot;\" lang=\"ja\"><li><span title=\"Godan verb with 'ru' ending\"..."
    },
    {
        "expression": "解る",
        "glossary": "<div style=\"text-align: left;\" class=\"rikaitan-glossary\"><i>(priority form, ★, jmdict.org [2025-05-13])</i> <span><ul style=\"list-style-type:&quot;＊&quot;\" lang=\"ja\"><li><span title=\"Godan verb with 'ru' ending\"..."
    }
]
```
