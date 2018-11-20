# abondance: Python library for Internet Health Report API

### Installation
Get the latest source files:
```
git clone git@github.com:InternetHealthReport/abondance.git
```

Install dependencies and install abondance:
```
cd abondance
sudo pip install -r requirements.txt 
sudo python setup.py install
```
## AS inter-dependency (AS hegemony)
### Example: Retrieve dependencies for AS2501 on September 15th, 2018
```python
from abondance.hegemony import Hegemony

hege = Hegemony(originasns=[2501], start="2018-09-15 00:00", end="2018-09-15 23:59")

for r in hege.get_results():
  print(r)
```

### Example: Retrieve dependents of AS2500 on September 15th, 2018
```python
from abondance.hegemony import Hegemony

hege = Hegemony(asns=[2500], start="2018-09-15 00:00", end="2018-09-15 23:59")

for r in hege.get_results():
  # Skip results from the global graph
  if r["originasn"] == 0:
    continue
  print(r)
```
