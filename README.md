# UPGMApy

UPGMApy is a basic implementation of the [UPGMA] (Unweighted Pair Group Method with Arithmetic Mean) algorithm, one of many used in bioinformatics (phylogenetics) for constructing [evolutionary trees]. (The typical data set is a matrix of molecular comparisons between species.)

The algorithm does this by repeatedly joining the columns and rows of the most similar (lowest-value) entries in the table until a final tree is constructed.

### Usage
To run the algorithm, simply supply UPGMA with a lower triangular matrix and a corresponding list of labels. The output will be a single label corresponding to the final tree.
```python
# Test table data and corresponding labels
M_labels = alpha_labels("A", "G") # Generates labels from "A" to "G"
M_data = [
    [],                         #A
    [19],                       #B
    [27, 31],                   #C
    [8, 18, 26],                #D
    [33, 36, 41, 31],           #E
    [18, 1, 32, 17, 35],        #F
    [13, 13, 29, 14, 28, 12]    #G
    ]
# Run UPGMA
UPGMA(M_data, M_labels)
```
For this test input, the output should be the following:
```python
'((((A,D),((B,F),G)),C),E)'
```

The above example comes from an article by [Dave Thomas]
### Todos

 - Add option for computing tree heights

   [UPGMA]: <https://en.wikipedia.org/wiki/UPGMA>
   [evolutionary trees]: <https://en.wikipedia.org/wiki/Phylogenetic_tree>
   [dave thomas]: <http://www.nmsr.org/upgma.htm>
   
   
### License
MIT