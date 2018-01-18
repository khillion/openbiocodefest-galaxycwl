# Use CWL on Galaxy - OpenBio Winter Codefest 2018

Here will be summed up the work done during the OpenBio WInter Codefest 2018 in Boston on the use of CWL in Galaxy.
The work is based on this [branch](https://github.com/common-workflow-language/galaxy) that tries to allow Galaxy ro run CWL tool. Many information about this branch is documented [HERE](https://github.com/common-workflow-language/galaxy/pull/47).

## Prerequisites

* Clone this [branch](https://github.com/common-workflow-language/galaxy)
* Install planemo (`pip install planemo`)

## Use cwl conformance tests to run a simple example

## Use planemo to run a simple example
**currently broken** @jmchilton is working on it.

```bash
mkdir galaxycwl
cd galaxycwl
git clone https://github.com/khillion/openbiocodefest-galaxycwl
virtualenv -p python venv
. venv/bin/activate
pip install planemo
planemo run --cwl --cwl_galaxy_root=galaxy 1st-tool.cwl echo-job.yml
```

