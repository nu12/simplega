# simplega

```simplega``` is a simple python implementation of genetic algorithm and it is available through PyPI.

## Install
```shell
python3 -m pip install simplega
```

## Usage

Import the package
```python
from simplega import Chromosome, Population, GA, GAHelper
# or
from simplega import *
```

Create a fitness function that suits your problem
```python
def maximize(chromosome):
    return sum( [ ord(gene) for gene in chromosome.dna ] )
```

Create a new instance of GA specifying the fitness function to be used
```python
ga = GA(maximize)
```

Perform the steps of the genetic algorithm and retrieve the fittest chromosome
```python
ga.run()
print(ga.get_fittest())
```

All the script - really simple:
```python
from simplega import *

def maximize(chromosome):
    return sum( [ ord(gene) for gene in chromosome.dna ] )
    
ga = GA(maximize)
ga.run()
print(ga.get_fittest())
```

### Advanced usage

You can customize your instance of GA, replacing any or all of its default values
```python
ga = GA(fitness_function, 
  genes =  [ chr(n) for n in range(65,91) ], 
  chromosome_size =  10, 
  population_size =  100, 
  generations =  100, 
  crossover_points =  1, 
  elitism_rate =  0.05, 
  crossover_rate =  0.85, 
  mutation_rate =  0.01, 
  )
```

You can print the fittest chromosome of each generation with ```ga.run(True)```

## Contributing

Please submit bugfixes, enhancements, unit tests, usecases and examples with a pull request.