#Example using Imposter with Docker and a 3rd party wsdl from Portico

#General Steps
1. Create .yaml with .wsdl reference (resources is optional. sample response returned without matching)
  - Can reference hardcoded .xml files or hardcode responses in .yaml

2. From directory with .wsdl and .yaml, run docker command to deploy
  - replace $PWD with %cd% on windows
  - docker run -ti -p 8080:8080 -v $PWD:/opt/imposter/config outofcoffee/imposter-all

3. Now, you'll notice docker downloaded the outofcoffee docker image, and deployed our configured imposter to a container running on port 8080

#Todo
- How do we enhance our request body search to contend with encoded xml in the response element? regular expression possible?
- Use the Portico .xsd files. The portico wsdl just lists methods, which is all I impored... although you can also try to import the separate xmls. Ours are old and unversioned and I saw some issues when I referenced them so skipping for Now

