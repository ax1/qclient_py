Follow https://packaging.python.org/tutorials/packaging-projects/

Do not use test, go to pypi.org directly.

After build and befor uploading, check project structure in folder dist/*.tar.xz

Create the ~/.pypirc file and add the following

```
[qclient]
  username = __token__
  password = pypi-aaaaabbbbbbccccddddd (token from pypi)
```

```
cd ./qclient (parent folder to src/ and dist/)
... (other commands)
python3 -m twine upload  dist/* (this is the only different since --repository did not work, also remove older versions before uploading)