## Tasks

1. Create a Dictionary in Python and write it to a json File.
A) import json then dumps or dump and write in file

2. Read a json file `services.json` kept in this folder and print the service names of every cloud service provider.

```
output

aws : ec2
azure : VM
gcp : compute engine

```
A)
import json

with open('services.json') as f:
    data = json.load(f)

for j, k in data['services'].items():
    if isinstance(k, dict):
        print(j, ":", k['name'])


3. Read YAML file using python, file `services.yaml` and read the contents to convert yaml to json
A)import yaml json >>open file >> yaml.safe_load >> json.dumps