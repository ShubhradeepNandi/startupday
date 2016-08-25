
#Natural Language Classifier

The Natural Language Classifier (NLC) is a service that can be trained and it 
is useful to describe how to create the steps to use it since it offers some cognitive learning features. 

Within Bluemix you can create an **unbound instance** of the NLC Service, by selecting Natural Language Classifier
in the Bluemix catalog.

![ScreenShot](images/nlc_service.png)
![ScreenShot](images/nlc_std_service.png)

Download the training file [csv](train.csv)

Train Your Classifier
```
curl -u "{username}":"{password}" -F training_data=@train.csv -F training_metadata="{\"language\":\"en\",\"name\":\"My Classifier\"}" "https://gateway.watsonplatform.net/natural-language-classifier/api/v1/classifiers"
```
##Using the NLC Service from Node-RED

You need to use the existing boilerplate sample.  It should finally look like this
![ScreenShot](images/nlc_complete.png)

Drag a Natural Language Classifier (NLC) node to the palette and click it to edit
![ScreenShot](images/nlc_edit_training.png)


Add the right Inject node to the palette and connect it with NLC
![ScreenShot](images/nlc_inject.png)

Add the right Debug node to the palette and connect it from NLC
![ScreenShot](images/nlc_payload.png)

##Run the NLC Service from Node-RED
Trigger the Inject node and see the Debug Console
![ScreenShot](images/nlc_debug.png)


The flows for this part of the lab are here -> [flows](code.json)
