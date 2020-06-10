# Mineria_de_Datos
Class Session
![Mineriade Datos](https://cdn.windowsreport.com/wp-content/uploads/2018/07/data-mining.png)


# Big-Data  

### <p align="center" > TECNOLÓGICO NACIONAL DE MÉXICO INSTITUTO TECNOLÓGICO DE TIJUANA SUBDIRECCIÓN ACADÉMICA DEPARTAMENTO DE SISTEMAS Y COMPUTACIÓN PERIODO: Enero - Junio 2020 </p>

###  <p align="center">  Carrera: Ing. En Sistemas Computacionales. Materia: 	Datos Masivos (BDD-1704 IF9A	).</p>

### <p align="center">  Maestro: Jose Christian Romero Hernandez	</p>
### <p align="center">  No. de control y nombre del alumno:  </p>
### <p align="center">  No. de control y nombre del alumno:16210585 - Valenzuela Rosales Marco Asael </p>
### <p align="center">  No. de control y nombre del alumno:13210388 - Ivan Adrian Torres Flores </p>



# Unit 4

## Index
&nbsp;&nbsp;&nbsp;[Exam](#[Exam)  
### &nbsp;&nbsp;Exam.
#### &nbsp;&nbsp;&nbsp;&nbsp; Instruccions.
```
Develop the following problem with R and RStudio for knowledge extraction
that the problem requires.
Implement the K-Means grouping model with the Iris.csv dataset that
found at https://github.com/jcromerohdz/iris using the method
kmeans () in R. Once the grouping model is obtained, do the analysis
corresponding data display.
At the end of the development, explain in detail the model of
K-Means group and what were their observations in visualization analysis of
data.
Assessment instructions
- Delivery time 4 days
- At the end put the code and the explanation in the corresponding branch of your
github also make its explanation of the solution on your google drive.
- Finally defend its development in a video of 8-10 min which will serve to give
Your rating, this video must be uploaded to YouTube to be shared by a link.


```
#### &nbsp;&nbsp;&nbsp;&nbsp; Code
getwd()
setwd("/home/marco/Escritorio/DataMining-master/Datasets")
getwd()


dataset <- read.csv('Iris.csv')
colnames(dataset) <- c("sepal_length", "sepal_width","petal_length","petal_width", "species")
dataset

dataset$species=NULL
dataset.scaled = as.data.frame(scale(dataset))

library(devtools)
devtools::install_github("kassambara/factoextra")

km <-kmeans(dataset.scaled,4)
km

aggregate(dataset.scaled, by = list(cluster = km$cluster),mean)

library(factoextra)

fviz_cluster(km, data = dataset.scaled)


```--------------------------------------------------------------------------------------------------------------------
The k-mean algorithm solves an optimization problem, the function to be optimized (minimized) being the sum of the quadratic distances of each object to the centroid of its cluster.
Clustering is a technique to find and classify K groups of data (clusters). Thus, the elements that contain similar characteristics are together in the same group, separated from the other groups with which they do not have specific characteristics.
To find out if the data is similar or different, the K-means algorithm uses the distance between the data. Observations that resemble a shorter distance between them. In general, the Euclidean distance is used as a measure, although other functions can also be used.

We will do the kmeans starting by saving a km variable and we will use the kmeans function of the stat package where the only thing we have is to indicate it is the data set that we already have the scaling and the number of divisions or groups that we will do in this case will be 4 can be done by divisions or by centers in this case we will use the divisions to do it this is repeated and repeated and the maximum can be done 10 times as we see here
km <-kmeans (dataset.scaled, 4)
km

as we can see in the cluster separates them by groups we have what percentage of the information is summarized in the cluster this is the sum of the squares of the values ​​of each cluster with respect to the total if we calculate the sum of the squares of the values ​​of each cluster and the sum of object objects that belongs in each group over the total gives us the percentage

aggregate (dataset.scaled, by = list (cluster = km $ cluster), mean)
it is to add the data set already scaled that by the list given the equal cluster of the km that we already have the variable cluster and this we will extract the average and give us the average of our data set

the library is used to visualize the cluster
library (factoextra)

fviz_cluster (km, data = dataset.scaled)

we will create a new variable, with our km with our data set already scaled

we run it and it shows us the graphs we have in each graph a darker than serious point the center of each group we have 2 dimensions in the x axis we have that is the Dim one that has 72.6 percent of the data and of the second dimension we have which is 23.1 percent of the data

```


