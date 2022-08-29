
# Privacy-Preserving Process Mining with PM4Py
To make privacy-preserving process mining more accessible, we integrated state-of-the-art differential privacy algorithms in *PM4Py*, the leading open source process mining platform written in *Python*. We provide the first integration of such anonymization techniques into a general process mining toolkit, and therefore making the respective algorithms more accessible to process mining experts and data scientists. To anonymize the control-flow of an event log, we integrated the *SaCoFa* algorithm and the *Laplacian* mechanism. To anonymize contextual information, we integrated the *PRIPEL* framework. *PM4Py* is a product of the *Fraunhofer Institute for Applied Information Technology*.

## Documentation

The documentation about our privacy preserving algorithms is offered in our demo abstract InserLinkToTheDemoAbstract and in our screencast InserLinkToTheScreencast

The documentation about *PM4Py* is offered at http://www.pm4py.org/

## First Example

```python
import pm4py
from pm4py.algo.anonymization.trace_variant_query import algorithm as trace_variant_query
from pm4py.algo.anonymization.pripel import algorithm as pripel
log = pm4py.read_xes("logName.xes")
epsilon = 0.01
sacofa_result = trace_variant_query.apply(log=log, variant=trace_variant_query.Variants.SACOFA, 
                                            parameters={"epsilon": epsilon, "k": 15, "p": 20})
anonymizedLog = pripel.apply(log=log, trace_variant_query=sacofa_result, epsilon=epsilon)
```

## Installation

When our work is aviabil in the offical PM4Py libary it can be used on Python 3.7.x / 3.8.x / 3.9.x / 3.10.x by invoking:
```bash
pip install -U pm4py
```

Now our work can be used by simply downloading this repository.
## Citing our work
....

## Citing pm4py
Please cite pm4py as follows:

Berti, A., van Zelst, S.J., van der Aalst, W.M.P. (2019): Process Mining for Python (PM4Py): Bridging the Gap Between Process-and Data Science. In: Proceedings of the ICPM Demo Track 2019, co-located with 1st International Conference on Process Mining (ICPM 2019), Aachen, Germany, June 24-26, 2019. pp. 13-16 (2019). http://ceur-ws.org/Vol-2374/

## Third Party Dependencies
As scientific library in the Python ecosystem, we rely on external libraries to offer our features.
In the */third_party* folder, we list all the licenses of our direct dependencies.
Please check the */third_party/LICENSES_TRANSITIVE* file to get a full list of all transitive dependencies and the corresponding license.
