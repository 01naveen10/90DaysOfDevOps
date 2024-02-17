
## Tasks

1. Give the Difference between List, Tuple and set. Do Handson and put screenshots as per your understanding.
A) list is similar to array ordered changable allows duplicate, tuple is same but unchangable and set is unchangeable unordered and doesn't allow duplicate elements

2. Create below Dictionary and use Dictionary methods to print your favourite tool just by using the keys of the Dictionary.

```
fav_tools =
{
  1:"Linux",
  2:"Git",
  3:"Docker",
  4:"Kubernetes",
  5:"Terraform",
  6:"Ansible",
  7:"Chef"
}
```
A) fav_tools[3]

3. Create a List of cloud service providers
   eg.

```
cloud_providers = ["AWS","GCP","Azure"]
```

Write a program to add `Digital Ocean` to the list of cloud_providers and sort the list in alphabetical order.
A)
def myfun(lis, x):
    lis.append(x)
    lis.sort()

myfun(cloud_providers, "Digital Ocean")
