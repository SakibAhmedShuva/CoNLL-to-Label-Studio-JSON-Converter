# CoNLL-to-JSON-Converter

This project provides a Jupyter notebook to convert CoNLL format files to Label Studio compatible JSON format. It's particularly useful for preparing named entity recognition (NER) datasets for using in Label Studio. Please see the "samples" folder to learn about the format of compatible CoNLL files.

## Features

- Converts CoNLL format to Label Studio JSON format
- Preserves sentence structure and token-level annotations
- Generates unique IDs for each annotation
- Includes metadata such as creation time and annotation statistics

## Requirements

- Python 3.6+
- JSON library (built-in)
- datetime library (built-in)

## Usage

1. Clone this repository:
   ```
   git clone https://github.com/SakibAhmedShuva/CoNLL-to-Label-Studio-JSON-Converter.git
   cd CoNLL-to-JSON-Converter
   ```

2. Run the notebook:
   ```
   conll2json.ipynb
   ```

2. Modify the `conll_file_path` variable in the script to point to your CoNLL file:
   ```python
   conll_file_path = r"path/to/your/conll/file.conll"
   ```
   
4. The converted JSON file will be saved as `labelstudio_output.json` in the same directory.

## Function Details

The main function `convert_conll_to_labelstudio` takes a CoNLL file path as input and returns a list of dictionaries, where each dictionary represents a sentence with its annotations in Label Studio format.

```python
def convert_conll_to_labelstudio(conll_file_path: str) -> List[Dict[str, Any]]:
    # Function implementation...
```

## Output Format

The output JSON file follows the Label Studio format, which includes:

- Sentence text
- Token-level annotations with start and end positions
- Metadata such as creation time, annotation counts, etc.

## Notes

- The script assumes that the CoNLL file uses space or tab as a delimiter and follows the standard CoNLL format (token, POS tag, chunk tag, NER tag).
- Empty lines or lines starting with '-DOCSTART-' are treated as sentence boundaries.
- The script generates a unique ID for each annotation to ensure compatibility with Label Studio.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the [MIT License](LICENSE).
