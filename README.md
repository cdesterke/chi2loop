# chi2loop
R-package to perform loop of chi.test on character columns of a dataset 

### Script used in the package

> data(models)

> results<-cltest(models)

> nlpplot(results,title="NLP plot on models")

abbreviations: NLP : negative log10 of chi.test p-values

![nlpplot](https://github.com/cdesterke/chi2loop/blob/main/nlpplot.png)

# network with louvain communities in package version 1.1.2
> chinet(results,fold=3)
### fold parameter reduce difference of size from the weighted edges

![chinet2](https://github.com/cdesterke/chi2loop/blob/main/chinet2.png)



