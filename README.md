# Information Systems
This repository is created for the Information Systems Journal submissions.

# Related Works
A detailed related works are presented <a href="./related_works.pdf">here</a>.

# Proof of Concept
You can find <a href="./purchase_request_20241016_0954.bos">here</a> a process model created directly by process developer on Bonita, and other convert the BPDML to Bonita ecosystem.
You should <a href="https://www.bonitasoft.com/">download</a> Bonita Studio, then import the .bos file to view the models and data implemented within Bonita Studio.

# TOOL
BPDML provides a Docker image to run the BPMN modeler as a Container in Docker.
The BPDML Docker image is based on the official NodeJS image (node:16-buster). The container image contains a prebuild appliction and exposes the port 3000. The port 3001 is used flask server that used to connect to the openAI API.


Run the following command after changing the <openai-key> and <bonita-workspace>. The <bonita-workspace> is used to connect our system to the Bonita ecosystem. In this case, we can directly connect to the Business Data Model defined within Bonita to define "Data store" objects. Also, it is important to export the BPDML to be executable within Bonita. Indeed, the <openai-key> is used for the transformation and validation of Gherkin from natural language to Groovy script code.

	$ docker pull anonymous4conferences/bpmn-tool:latest
	$ docker run --name="bpmn-tool" --rm -p 3000:3000 -p 3001:3001  --env OPENAI_KEY=<open-api-key> -it -v <bonita-wokspace>:/usr/src/app/bonita anonymous4conferences/bpmn-tool


The application can be started from a web browser (if you add the Bonita workspace, you should use this workspace). You can run your tool without a Bonita workspace and without an OpenAI key, but it will not be executable for modeling purposes.
    
    http://localhost:3000/#/usr/src/app/workspace


<img
src="./tool/Screenshot (20).png"
width = "250"
raw=true
/>
<img
src="./tool/Screenshot 2023-07-31 120558.png"
width = "250"
raw=true
/>
<img
src="./tool/Screenshot 2023-07-31 120614.png"
width = "250"
raw=true
/>
<img
src="./tool/Screenshot 2023-11-08 150844.png"
width = "250"
raw=true
/>
# RUNNING EXAMPLE
<img
src="./tool/Screenshot 2023-11-03 123201.png"
width = "250"
raw=true
/>
<img
src="./tool/Screenshot 2023-11-03 123754.png"
width = "250"
raw=true
/>


# EVALUATIONS
The evaluation details are <a href="./Evaluation__Evaluation.pdf">here</a>. Also, in the "prompts" folder you can find our prompts, and in "scenarios", all the scenarios we are used within our evaluation.
