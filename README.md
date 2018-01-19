# Use CWL on Galaxy - OpenBio Winter Codefest 2018

Here will be summed up the work done during the OpenBio Winter Codefest 2018 in Boston on the use of CWL in Galaxy.
The work is based on this [branch](https://github.com/common-workflow-language/galaxy) that tries to allow Galaxy ro run CWL tool.

## Prerequisites

* Clone this [branch](https://github.com/common-workflow-language/galaxy)
* Install planemo (`pip install planemo`)

## Use cwl conformance tests to run a simple example
Conformance tests are run in galaxy by "mirroring" the conformance tests from the [branch](https://github.com/common-workflow-language/common-workflow-language) into the galaxy test folder (`test/functional/tools/cwl_tools`). The script conformance_to_test_cases.py converts the tests defined in test/functional/tools/cwl_tools/v1.0/conformance_tests.yaml to galaxy test cases located in test/api/test_cwl_conformance_v1_0.py. these can be run with the run_tests.sh script of galaxy root folder.
For instance, to run all of the conformance tests:

```bash

```

and to run one in particular:

```bash

```

## run cwl tools and workflows directly in galaxy from the command line
@jmchilton created a script called run_cwl in the scripts folder of the galaxy-cwl branch. This script allows to run cwl jobs from the command line using a syntax close to that of cwl-runner. To run it:

1. Launch Galaxy with run.sh
2. Go to 127.0.0.1 and copy the admin API key provided
3. run it using 

```bash
source .venv/bin/activate
python scripts/run_cwl.py --api_key [your api key] [path to cwl file] [path to job definition file]
``` 
It prints out the job result sumary JSON, but does not download locally the job result files (for now at least).

# Use planemo to run a simple example
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
