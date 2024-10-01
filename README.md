# Filter Query Generator

A web-based tool that converts indicators (like phrases, domains, IP ranges, etc.) into filter queries.

## Description

The **Filter Query Generator** allows you to input various indicators and automatically generates the corresponding filter queries based on the selected indicator type. This tool is designed for ease of use and ensures that all data processing is done locally within your browser for maximum privacy and security.

## Features

- **Multiple Indicator Types:**
  - Phrase
  - Word
  - Email Domain (Corporate)
  - Domain
  - IP Range
  - Typo-Squatting
- **Flexible Input Methods:**
  - Enter indicators on separate lines to generate individual filter queries.
  - Enter multiple indicators on the same line, separated by spaces, to combine them into a single filter query.
- **Automatic Output Generation:**
  - Real-time generation of filter queries as you type.
  - Output matches the required format for each indicator type.
- **Copy to Clipboard:**
  - Easily copy the generated filter queries with a single click.
- **Local Processing:**
  - All data is processed locally in your browser; no data is sent to any server.

## Requirments

- A modern web browser (e.g., Chrome, Firefox, Edge, Safari).

## Usage

1. **Select Indicator Type**

   At the top of the page, use the dropdown menu to select the desired indicator type.

2. **Enter Indicators**

   - **Separate Lines:**

     Enter each indicator on a new line in the left text box.

     **Example:**

     ```
     test.com
     test2.com
     ```

   - **Same Line with Spaces:**

     Enter multiple indicators on the same line, separated by spaces.

     **Example:**

     ```
     test.com test2.com
     ```

3. **View Generated Filter Queries**

   The right text box will automatically display the generated filter queries based on your input and the selected indicator type.

4. **Copy to Clipboard**

   Click the "Copy to Clipboard" button below the text boxes to copy the generated filter queries for use elsewhere.

## Examples

### Example 1: Single Indicators per Line

**Input (Left Box):**

```
test.com
example.com
```

**Selected Indicator Type:**

```
Domain
```

**Output (Right Box):**

```
(domain:'test.com')
(domain:'example.com')
```

### Example 2: Multiple Indicators on the Same Line

**Input (Left Box):**

```
attack breach data
```

**Selected Indicator Type:**

```
Phrase
```

**Output (Right Box):**

```
(phrase:'attack')+(phrase:'breach')+(phrase:'data')
```

### Example 3: Combination of Both

**Input (Left Box):**

```
test.com test2.com
example.com
```

**Selected Indicator Type:**

```
IP Range
```

**Output (Right Box):**

```
(iprange:'test.com')+(iprange:'test2.com')
(iprange:'example.com')
```

## Code Structure

- **HTML:** Structure of the webpage, including the dropdown menu, text areas, and buttons.
- **CSS:** Styling for the webpage to enhance user experience.
- **JavaScript:** Handles input processing, output generation, and clipboard functionality.


## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or additions.


## Author

- **alenperic** - [GitHub Profile](https://github.com/alenperic)

## Acknowledgments

- Inspired by the need for secure, local processing tools in cybersecurity.
- Based on prior tools developed for text and data processing.

