MMP_SMS
=======

Module for Titanium, which helps user to integrate native iOS SMS view to Titanium App.

Step to integrate the module with your project:

	1. Unzip the zip file
	2. Copy the com.midhun.sms folder to your Appcelerator titanium's iPhone module folder.
           If you didn't changed the install path the normal path will be:
           `~/Library/Application Support/Titanium/modules/iphone`
	3. Go to the TiApp Editor page of your project.
		a. If you are using the GUI interface add the module on the right side window.
		b. If you are using the xml file, add the below lines to your tiapp.xml.
```
			<modules>
        			<module platform="iphone" version="1.0">com.midhun.sms</module>
    			</modules>
```

#####Create the message composer:
```
	var smsModule = require('com.midhun.sms');
        var smsDialog = smsModule.createMessage({
   		receivers: ['+91 9846389231'],
    		messageBody: 'Hi Midhun',
    		barColor: 'black'});
    	if(smsDialog.isSupported())
    	{
    		smsDialog.open({animated: true});
    		smsDialog.addEventListener('complete',function(e){
        		if(e.result == smsDialog.SENT)
        		{
        			var successAlert = Ti.UI.createAlertDialog({
        				title : 'Message Sent',
        				message : 'Hurray',
        				buttonNames : ['OK']
        			});
        			successAlert.show();
	        	}
        	});
       }

```

For Further Details Contact:

	Midhun M P
	Email : midhunmp7@gmail.com
	Mobile: +91 9846389231