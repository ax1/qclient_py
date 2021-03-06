# qclient

Client for running quantum applications on qserver instances. See https://quantum.tecnalia.com.

## Install

```sh
pip install qclient
```

## Usage

```python
import qclient

qclient.configure({'token': 'YOUR_TOKEN'})
print(qclient.get('bell'))
print(qclient.execute('bell'))
print(qclient.execute(circuit.qasm()))
```

# Methods

- **configure({ server?, ext? ,token? })**: `server`: default server at https://quantum.tecnalia.com. `ext`: default '.qasm', useful in case always using the same language to represent the algorithm. `token`: default '', authorization token to execute services. E.g.: `configure({"token':'kkajsdkj-sudiuawjd...."})`.
- **get(algorithm_name)**: the algorithm in plain text, the extension of the file is optional. E.g.: `get('bell')`.
- **execute(algorithm_name or algorithm_description)**: based on the extension, an engine executes the algorithm and provides the result as string (depending on the engine, the result format can vary). E.g.: `execute('bell')`. If the algorithm is not stored yet, it can be executed by providing the text representation (in qasm, quil, etc.). E.g: execute('...qasm_string').
