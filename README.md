# xl
Parsing google results

To install:	```pip install xl```

## Overview
The `xl` package is designed for parsing Google search results HTML pages. It provides a comprehensive set of tools to extract various pieces of information from Google search results, such as the number of results, ads, organic results, related searches, and more. The package utilizes BeautifulSoup for parsing HTML content and provides a structured output in the form of dictionaries that can be easily used for further data analysis or processing.

## Main Features
- **Parsing Google Search Results**: Extract detailed information from Google search result pages.
- **Support for Multiple Result Types**: Handles organic results, ads, related searches, and other components found in Google search pages.
- **Output as Structured Data**: Converts HTML content into structured dictionaries, making it easier to handle and analyze.
- **Utility Functions**: Includes several utility functions to assist with tasks such as file handling and URL processing.

## Installation
To install the package, run the following command:
```bash
pip install xl
```

## Usage Examples

### Parsing a Google Search Result HTML File
To parse a Google search result from an HTML file and extract information:
```python
from xl import mk_gresult_tag_dict, parse_tag_dict

# Path to your HTML file
file_path = 'path_to_your_google_search_result.html'

# Create a tag dictionary from the HTML file
tag_dict = mk_gresult_tag_dict(file_path)

# Parse the tag dictionary to get a structured information dictionary
info_dict = parse_tag_dict(tag_dict)

# Print the extracted information
print(info_dict)
```

### Extracting Domain Lists from Google Results
To get a list of domains from the parsed Google search results:
```python
from xl import get_domain_list_from_google_results

# Assuming `info_dict` is already obtained from previous steps
domain_list = get_domain_list_from_google_results(info_dict)

# Print the list of domains
print(domain_list)
```

## Function Documentation

### `mk_gresult_tag_dict(input)`
Takes a BeautifulSoup object, HTML string, or filename of a Google result HTML and returns a dictionary containing key components of interest from the HTML.

### `parse_tag_dict(tag_dict)`
Takes a dictionary (generated by `mk_gresult_tag_dict`) and parses it to extract structured information such as the number of results, lists of ads, and organic results.

### `get_domain_list_from_google_results(gresults)`
Accepts either a BeautifulSoup object, HTML content, or a filename and returns a list of domains extracted from the Google search results.

## Contributing
Contributions to the `xl` package are welcome. Please ensure that your code adheres to the existing style and that all tests pass before submitting a pull request.

## License
This project is licensed under the MIT License - see the LICENSE file for details.