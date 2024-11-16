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
- **Additional Toggle Options:**
  - **Dedicated Leak Sites:** When enabled, appends `+(source_category:'dedicated_leak_site')` to each filter query.
  - **Code Repository Monitoring:** When enabled, appends a group of code repository monitoring terms to each filter query.
- **Automatic Output Generation:**
  - Real-time generation of filter queries as you type.
  - Output matches the required format for each indicator type, with correct use of operators.
- **Copy to Clipboard:**
  - Easily copy the generated filter queries with a single click.
- **Local Processing:**
  - All data is processed locally in your browser; no data is sent to any server.

## Requirements

- A modern web browser (e.g., Chrome, Firefox, Edge, Safari).

## Usage

1. **Select Indicator Type**

   At the top of the page, use the dropdown menu to select the desired indicator type.

2. **Toggle Options**

   - **Dedicated Leak Sites:** Toggle this option on or off depending on whether you want to include `+(source_category:'dedicated_leak_site')` in your filter queries.
   - **Code Repository Monitoring:** Toggle this option on or off depending on whether you want to include code repository monitoring terms in your filter queries.

3. **Enter Indicators**

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

4. **View Generated Filter Queries**

   The right text box will automatically display the generated filter queries based on your input, the selected indicator type, and the state of the toggles.

5. **Copy to Clipboard**

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

**Toggle Options:**

- **Dedicated Leak Sites:** Off
- **Code Repository Monitoring:** Off

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

**Toggle Options:**

- **Dedicated Leak Sites:** Off
- **Code Repository Monitoring:** Off

**Output (Right Box):**

```
(phrase:'attack')+(phrase:'breach')+(phrase:'data')
```

### Example 3: Using Dedicated Leak Sites Toggle

**Input (Left Box):**

```
test.com
example.com
```

**Selected Indicator Type:**

```
Domain
```

**Toggle Options:**

- **Dedicated Leak Sites:** On
- **Code Repository Monitoring:** Off

**Output (Right Box):**

```
(domain:'test.com')+(source_category:'dedicated_leak_site')
(domain:'example.com')+(source_category:'dedicated_leak_site')
```

### Example 4: Using Code Repository Monitoring Toggle

**Input (Left Box):**

```
test
```

**Selected Indicator Type:**

```
Phrase
```

**Toggle Options:**

- **Dedicated Leak Sites:** Off
- **Code Repository Monitoring:** On

**Output (Right Box):**

```
(phrase:'test')+(keyword:'api_key',keyword:'secret_key',keyword:'access_token',keyword:'refresh_token',keyword:'bearer_token',keyword:'oauth_token',keyword:'jwt_secret',keyword:'db_password',keyword:'database_url',keyword:'connection_string',keyword:'mongo_uri',keyword:'aws_access_key_id',keyword:'aws_secret_access_key',keyword:'azure_connection_string',keyword:'gcp_credentials',keyword:'private_key',keyword:'public_key',keyword:'encryption_key',keyword:'decryption_key',keyword:'app_secret',keyword:'app_id',keyword:'consumer_key',keyword:'consumer_secret',keyword:'passwd',keyword:'pwd',keyword:'user:pass',keyword:'username:password',keyword:'api_token',keyword:'secret_token',keyword:'prod_',keyword:'dev_',keyword:'test_',keyword:'_key',keyword:'_secret',keyword:'_token')
```

*Note: The list of code repository monitoring terms is appended to each line.*

### Example 5: Both Toggles On

**Input (Left Box):**

```
test
```

**Selected Indicator Type:**

```
Phrase
```

**Toggle Options:**

- **Dedicated Leak Sites:** On
- **Code Repository Monitoring:** On

**Output (Right Box):**

```
(phrase:'example')+(keyword:'api_key',keyword:'secret_key',keyword:'access_token',keyword:'refresh_token',keyword:'bearer_token',keyword:'oauth_token',keyword:'jwt_secret',keyword:'db_password',keyword:'database_url',keyword:'connection_string',keyword:'mongo_uri',keyword:'aws_access_key_id',keyword:'aws_secret_access_key',keyword:'azure_connection_string',keyword:'gcp_credentials',keyword:'private_key',keyword:'public_key',keyword:'encryption_key',keyword:'decryption_key',keyword:'app_secret',keyword:'app_id',keyword:'consumer_key',keyword:'consumer_secret',keyword:'passwd',keyword:'pwd',keyword:'user:pass',keyword:'username:password',keyword:'api_token',keyword:'secret_token',keyword:'prod_',keyword:'dev_',keyword:'test_',keyword:'_key',keyword:'_secret',keyword:'_token')+(source_category:'dedicated_leak_site')
```

## Code Repository Monitoring Terms

The following terms are included when the **Code Repository Monitoring** toggle is enabled:

- **Authentication-related:**
  - api_key
  - secret_key
  - access_token
  - refresh_token
  - bearer_token
  - oauth_token
  - jwt_secret
- **Database-related:**
  - db_password
  - database_url
  - connection_string
  - mongo_uri
- **Cloud service-related:**
  - aws_access_key_id
  - aws_secret_access_key
  - azure_connection_string
  - gcp_credentials
- **Encryption-related:**
  - private_key
  - public_key
  - encryption_key
  - decryption_key
- **Application-specific:**
  - app_secret
  - app_id
  - consumer_key
  - consumer_secret
- **Variations and formats:**
  - passwd
  - pwd
  - user:pass
  - username:password
  - api_token
  - secret_token
- **Common prefixes and suffixes:**
  - prod_
  - dev_
  - test_
  - _key
  - _secret
  - _token

## Code Structure

- **HTML:** Structure of the webpage, including the dropdown menu, text areas, buttons, and toggle switches.
- **CSS:** Styling for the webpage to enhance user experience, including styles for the switches.
- **JavaScript:** Handles input processing, output generation, and clipboard functionality.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or additions.

## Author

- **alenperic** - [GitHub Profile](https://github.com/alenperic)

## Acknowledgments

- Inspired by the need for secure, local processing tools in cybersecurity.
- Based on prior tools developed for text and data processing.

**Note:** All data processing is done locally in your browser to ensure maximum privacy and security. No data is sent to any server.
