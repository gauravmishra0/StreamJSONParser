# StreamJSONParser

StreamJSONParser is a JavaScript module that provides a way to parse JSON data from a readable stream in an asynchronous and efficient manner. It is particularly useful when dealing with streaming JSON data, such as data received from server-sent events (SSE) or other real-time data sources.

## Installation

You can install StreamJSONParser using npm or yarn:

```shell
npm install stream-json-parser
```

or

```shell
yarn add stream-json-parser
```

## Usage

To use StreamJSONParser, you need to import it into your JavaScript or TypeScript code:

```javascript
import streamJSONParser from 'stream-json-parser';
```

### Example Usage

Here is an example of how to use StreamJSONParser to parse JSON data from a readable stream:

```javascript
import streamJSONParser from 'stream-json-parser';

// Create a ReadableStream (e.g., from a fetch response)
const response = await fetch('https://example.com/streaming-data');
const stream = response.body;

// Create a JSON parser for the stream
const parser = streamJSONParser(stream);

// Iterate over parsed JSON objects
for await (const jsonObject of parser) {
  // Handle each JSON object as it arrives
  console.log(jsonObject);
}
```

### How It Works

The `streamJSONParser` function accepts a readable stream as its input and returns an asynchronous generator that yields parsed JSON objects as they are received from the stream.

- The `readChunks` function reads the stream in chunks, asynchronously yielding each chunk.

- The `readLines` function processes the chunks to split them into lines of text. It handles cases where a single chunk might contain multiple lines.

- The main `streamJSONParser` function trims each line of text, removes any "data: " prefix, and parses the resulting JSON. It then yields the parsed JSON objects.

## Contributing

If you'd like to contribute to StreamJSONParser, please open an issue or submit a pull request on [GitHub](https://github.com/your/repo).

## License

StreamJSONParser is licensed under the [MIT License](LICENSE).

## Acknowledgments

StreamJSONParser is inspired by the need for efficient parsing of streaming JSON data in real-time applications.

## About

StreamJSONParser is maintained by [Your Name]. You can contact me at [your.email@example.com].

For more information, visit the [GitHub repository](https://github.com/your/repo).

---

**Note:** Replace `[your/repo]`, `[Your Name]`, `[your.email@example.com]`, and `[MIT License]` with your actual repository URL, name, contact information, and license information.

This README is a template, and you should customize it according to your project's specific details.