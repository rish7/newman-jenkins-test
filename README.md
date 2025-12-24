# newman-jenkins-test
This is test sample using CICD Jenkins and Newman 


`npm install -g newman`

`npm install -g newman-reporter-html`

`npm install -g newman-reporter-htmlextra`


### Basic Newman Command
The core command to run a collection:
`newman run your_collection.json`
### To include an environment file:
`newman run your_collection.json -e your_environment.json`
### For globals (if used):
`newman run your_collection.json -e your_environment.json -g your_globals.json`

