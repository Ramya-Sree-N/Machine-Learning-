### Different ways of creating python environment

#### Only Python Installed:

**1.** create a folder ABC ->
 go to the current directory of ABC ->
Now create the environment
```
python -m venv myenv

```
Now Activate the environment
```
myenv\Scripts\activate
```
After we activate now we can install any packages.
```
Examples: pip install numpy, pip install pandas
```

#### Using Linux Commands:
Create the environment
```
pip install virtualenv
```
install the python 
```
virtualenv -p python3 virtual_env
```
activate the environment
```
virtual_env\Scripts\activate
```

#### Using ANACONDA
First Install the Anaconda form the google.

Create the environment 
```
conda install -p venv python==3.12.4
```
Now Activate the environment
```
venv\Scripts\activate
```


