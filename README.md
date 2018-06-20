# abbyy-ocr-basic-example

1.) Open the parent folder in Terminal window



2.) Run the following command line to install the required packages:

pip install -r requirements.txt



3.) Set the environment variables: ABBYY_APPID to your Application ID, ABBYY_PWD to the
Application Password. 
The processing server requires the Application ID and Password for each request. 
More details can be found in **APPENDIX.

On Windows operating system, this is done with the following commands:

set ABBYY_APPID=YourApplicationId
set ABBYY_PWD=YourPassword

On Linux operating system, use these commands:

export ABBYY_APPID=YourApplicationId
export ABBYY_PWD=YourPassword

For this project, you can simply add credentials to AbbyyOnlineSdk.py to the variables
already defined.



4.) Run image recognition:

python process.py "image.jpg" result.txt



5.) By default, the sample is configured to recognize documents in English and export them    
to plain text format (TXT). Other languages and settings are available through 
command-ine options. To see the possible options, run:

python process.py -h



6.) Change the code of the sample to integrate OCR with other functionality your   
application will provide and create the best solution for your scenario.




**APPENDIX:

C# sample
// Create a Web request and 
// setup it with the correct Application ID and Application Password

String url = "http://cloud.ocrsdk.com/processImage?Language=English,Russian";
WebRequest request = WebRequest.Create( url );

Encoding encoding = Encoding.GetEncoding("iso-8859-1");
string toEncode = ApplicationID + ":" + ApplicationPassword;
string baseEncoded = Convert.ToBase64String(encoding.GetBytes(toEncode));

request.Headers.Add( "Authorization", "Basic " + baseEncoded ); 
//The request now has authentication header set up correctly



FOR MORE INFO, CHECK Cloud OCR SDK Documentation
Home > Support > Documentation > Quick Start Guides > Quick Start with OCR SDK for Python

Quick Start with OCR SDK for Python: https://ocrsdk.com/documentation/quick-start-guide/python-ocr-sdk/
