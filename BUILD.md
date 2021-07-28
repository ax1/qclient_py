Follow https://packaging.python.org/tutorials/packaging-projects/

Do not use test, go to pypi.org directly.

After building and before uploading, check project structure in folder dist/*.tar.gz

Create the ~/.pypirc file and add the following:

```
[qclient]
  username = __token__
  password = pypi-aaaaabbbbbbccccddddd (token from pypi)
```

Then execute the commands:

```
cd ./qclient (parent folder to src/ and dist/)
[... other commands if first time]
python3 -m build
python3 -m twine upload  dist/*version* (this is the only different since --repository did not work)
```