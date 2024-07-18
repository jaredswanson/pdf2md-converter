# PDF to Markdown Converter

This command-line tool converts PDF files to well-formatted Markdown using the Ollama library. It provides an easy way to transform PDF content into a more versatile Markdown format.

## Features

- Convert PDF files to Markdown format
- Use Ollama models for intelligent conversion (default: gemma2:9b)
- Specify custom output directories
- Configure preferred Ollama model via command-line or configuration file
- Easy to use command-line interface

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Python 3.x installed on your system
- Ollama service running with the desired model available (default: gemma2:9b)

## Installation

1. Clone this repository or download the `pdf2md` script.

2. Install the required Python packages:

   ```
   pip install PyPDF2 ollama
   ```

3. Make the script executable:

   ```
   chmod +x pdf2md
   ```

4. Move the script to a directory in your PATH, for example:

   ```
   sudo mv pdf2md /usr/local/bin/
   ```

   Alternatively, you can add the script's directory to your PATH by adding the following line to your shell configuration file (e.g., `~/.bashrc`, `~/.zshrc`, or `~/.bash_profile`):

   ```
   export PATH="/path/to/script/directory:$PATH"
   ```

   Replace "/path/to/script/directory" with the actual path where your script is located.

5. If you modified your shell configuration file, reload it:

   ```
   source ~/.bashrc  # or ~/.zshrc, ~/.bash_profile, etc.
   ```

## Usage

Convert a PDF file to Markdown:

```
pdf2md input.pdf
```

This will create a Markdown file with the same name as the input PDF in the current directory.

To specify a custom output directory:

```
pdf2md input.pdf -o /path/to/output/directory
```

To use a specific Ollama model:

```
pdf2md input.pdf -m llama2:13b
```

For help and to see all available options:

```
pdf2md --help
```

## Configuration

The script uses a configuration file (`pdf2md_config.json`) to store the preferred Ollama model. If you specify a model using the `-m` or `--model` option, it will be saved in this file for future use.

You can manually edit the configuration file to set your preferred model:

```json
{
  "model": "gemma2:9b"
}
```

If no configuration file exists, the script will use the default model (gemma2:9b).

## How It Works

1. The script reads the content of the PDF file.
2. It sends the extracted text to the specified Ollama model (default: gemma2:9b).
3. The model processes the text and returns well-formatted Markdown.
4. The script saves the Markdown content to a file.

## Troubleshooting

- Ensure that the Ollama service is running and the specified model is available.
- Check that you have the necessary permissions to read the input PDF and write to the output directory.
- If you encounter any Python-related errors, verify that all required packages are installed correctly.

## Contributing

Contributions to improve the PDF to Markdown Converter are welcome. Please feel free to submit a Pull Request.

## License

This project is open source and available under the [MIT License](LICENSE).

## Contact

If you have any questions or feedback, please open an issue in the GitHub repository.

Happy converting!
