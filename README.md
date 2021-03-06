An implementation of a fun weather simulator in Scala programming language.

The fun journey continues.


    Technology stack
       - Scala 
       - Apache Spark MLlib 
       - Predictive modelling 
       - Random Forests (Classification and Regression) 
       - LIBSVM data format for training data

    Key features
       - Increased model accuracy by increaing training data size and quality 
       - Flexible for future extensions 

    Simulation methodology 
       - The environment (atmosphere, topography, geography and oceanography) is summarised by the
         training samples with the attributes of position, time, weather conditions and sensor measurements  
       - Struture the enviroment and observations into training sets (in LIBSVM format):
           - Condition.txt
           - Temperature.txt
           - Pressure.txt
           - Humidity.txt
       - Build classification model for weather conditions 
       - Build regression models for weather sensors measurements (Temperature/Pressure/Humidity) 
       - Feed new data (time&location) the established predictive models to generate the simulated weather data

    Usage
       - sbt test or ./activator test 
       - sbt run or ./activator run
       - sbt "run-main com.funweather.WeatherSimulator"
       - sbt "run-main com.funweather.WeatherSimulator [latitude] [longitude] [elevation] [time stamp] 
       - Users may also want to modify or add test scenarios in WeatherSimulator.scala and ./activator run from terminal
       - Open the sbt project using your favorite IDE and run the tests and WeatherSimulator 
            - If IntelliJ encounters error 
                    thread "main" java.lang.IllegalArgumentException: System memory 259522560 must be at least 4.718592E8. Please ...
              set the VM options in Run/Debug Configurations to: -Xms128m -Xmx512m -XX:MaxPermSize=300m -ea

    TODO
       - Use R package rscala to integrate R scripts in fun-with-weather-R to produce training data and for
         data visualisation
       - Add training set from real weather data to make the simulation more realistic 
       - Feature engineering to extract more information from the time stamps, i.e. hour of the day, month of the 
         year to increase model accuracy
         
    Miscellaneous
       - Random Forest
            The pick of the Machine Learning algorithm is Random Forest:
                 1. Machine Learning
                    > Random Forest can be less prone to overfitting. Training more trees in a Random Forest reduces
                      the likelihood of overfitting because of the variance reduction from avaraging multiple trees in the forest
                    > Invariant under scaling and various other transformations of feature values, is robust to inclusion of
                      irrelevant features, and produces inspectable models
                    > Random forests can be used to rank the importance of variables in a regression or classification problem
                      in a natural way
                 2. Software Engineering
                    > One of the most successful machine learning models for classification and regression
                    > Ensembles of decision trees; simple numerical optimization; easy to understand and implement
                    > Easy tunning for peformance (accuracy and speed)
                 3. Big Data
                    > Can be implemented as distributed and parallel algorithm (i.g. Apache Spark MLlib implementation of Random Forest)
       
       - Scala and Apache Spark
            > Functional languages such as Scala allow us to represent mathematical concepts naturally, e.g. Probability Monad
            > Functional languages such as Scala, by promoting and encouraging immutability, are well suited to parallel or cluster computing,
              i.g., Apache Spark MLlib
