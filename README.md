# Python client generator for OpenAPI schema

## Requirements
Python 3.7+  
Docker engine. [Documentation](https://docs.docker.com/engine/install/)

## Usage
To generate the client, execute the following script
```bash
python ./generator/generate.py [--file <a path or URL to a .yaml file>] [--asyncio]
```

### Arguments:

**--file**  
Specifies the input OpenAPI specification file path or URL. This argument is required for generating the Python client. The input file can be either a local file path or a URL pointing to the OpenAPI schema.

**--asyncio**  
Flag to indicate whether to generate asynchronous code. If this flag is provided, the generated Python client will include asynchronous features. By default, synchronous code is generated.

### Saving Arguments:

The script saves provided arguments for future use. Upon the initial execution, if no arguments are provided, the script will check if there are previously saved arguments in the specified file path. If saved arguments are found, they will be loaded and used for generating the client. If no saved arguments are found or if new arguments are provided, the script will save the provided arguments for future use.

This mechanism ensures that users can omit specifying arguments on subsequent executions if the same arguments were used previously. Saved arguments are stored in a JSON file located at generator/args.json.

### Examples:
```bash
python ./generator/generate.py --file https://<domain>/openapi.json
python ./generator/generate.py --file https://<domain>/openapi.json --asyncio
python ./generator/generate.py --file /<path>/openapi.yaml
python ./generator/generate.py --file /<path>/openapi.yaml --asyncio
python ./generator/generate.py
```
