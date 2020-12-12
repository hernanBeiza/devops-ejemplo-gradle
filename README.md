# Getting Started

## Windows

### Compile Code
* gradle clean build

### Test Code
* gradle clean test

### Jar Code
* gradle clean build

### Run Jar
* Local:      gradle bootRun 
* Background: nohup bash gradle bootRun &

### Testing Application
* Abrir navegador: http://localhost:8081/rest/mscovid/test?msg=testing

## Linux

### Compile Code
* gradle clean build

### Test Code
* gradle clean test

### Jar Code
* gradle clean build

### Run Jar
* Local:      gradle bootRun 
* Background: nohup bash gradle bootRun &

### Testing Application
* curl -X GET 'http://localhost:8081/rest/mscovid/test?msg=testing'
