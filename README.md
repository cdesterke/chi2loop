# chi2loop

chi2loop R-package was designed to perform 2 by 2 loops of chi.square tests between categrorial variables defined as character columns in imported dataset. 

The first step with the "cltest" function is to perform iterative tests between columns to obtained a dataframe of results.
In second step it is possible to design a NLPplot with the function "nlpplot" on the results data.frame. This nlpplot represent colored bubble with proportional size relative to the negative log10 transformation of the chi.square test p-values. This nlpplot could be done on raw results of chi.square test or after fitration to considerate only significant ones (p-values < 0.05).

In a third step, still on chi.square test results, with the "chinet" function, it is possible to draw a clustering graph based on Louvain algorithm showing the clusters of variable dependencies. The size of the edges between the nodes is proportional to the p-values obtained between the variables so reflecting their association.

### Script used in the package

> data(models)

> results<-cltest(models)

> nlpplot(results,title="NLP plot on models")

abbreviations: NLP : negative log10 of chi.test p-values

![nlpplot](https://github.com/cdesterke/chi2loop/blob/main/nlpplot.png)

### network with louvain communities detection
> chinet(results,fold=3)

fold parameter reduce difference of size from the weighted edges

![chinet2](https://github.com/cdesterke/chi2loop/blob/main/chinet2.png)

### remarks

- cltest works on columns which are defined as.character so this function do not works on columns defined as.factor. During import of your dataset in R specify the parameter "stringsAsFactors=FALSE" 

- after cltest to perform graphics you can filter rows with significant results such as

> library(dplyr)

> results%>%filter(p.value<=0.05)->results

### references

> chisq.test R function in stats library: https://stat.ethz.ch/R-manual/R-devel/library/stats/html/chisq.test.html accessed on 2022, september 19th 
