# Docker-troubleshoot  
Record some probelms, when using Docker.(Just README file this repository)  

## some Docker **command**  

docker ps  
(Show running containers)  
docker ps -a   
docker ps -a --filter "ancestor=sha256:1a86f4dacc3fb28abda390e303fab1bc0849683bd2bb932095a3de43cafe1659"  
(Show all containers created based on this image, including running and stopped ones.)  

For delete image:  
docker stop <container_id>  
docker rm <container_id>  

## some Docker **problem**

> **1.** INFO:&nbsp; &nbsp; &nbsp; &nbsp; ::1:56416 - "POST /predict HTTP/1.1" 500 Internal Server Error  
ERROR:&nbsp; &nbsp; &nbsp; &nbsp; Exception in ASGI application  
Traceback (most recent call last):  
&nbsp; &nbsp; &nbsp; &nbsp; File "xxx **omitted** Multiple lines here xxx"  
http.client.RemoteDisconnected: Remote end closed connection without response  
During handling of the above exception, another exception occurred:  
Traceback (most recent call last):  
&nbsp; &nbsp; &nbsp; &nbsp; File "xxx **omitted** Multiple lines here xxx"  
&nbsp; &nbsp; &nbsp; &nbsp; raise RemoteDisconnected("Remote end closed connection without"  
urllib3.exceptions.ProtocolError: ('Connection aborted.', RemoteDisconnected('Remote end closed connection without response'))  
During handling of the above exception, another exception occurred:  
Traceback (most recent call last):  
&nbsp; &nbsp; &nbsp; &nbsp; File "xxx **omitted** Multiple lines here xxx"  
&nbsp; &nbsp; &nbsp; &nbsp; raise ConnectionError(err, request=request)  
requests.exceptions.ConnectionError: ('Connection aborted.', RemoteDisconnected('Remote end closed connection without response'))  

> **2.** curl : { "error": "Malformed request: GET /v1/models/***:predict" }  
所在位置 行:1 字符: 1  
\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~  
&nbsp; &nbsp; &nbsp; &nbsp; \+ CategoryInfo&nbsp; &nbsp; &nbsp; &nbsp; : InvalidOperation: (System.Net.HttpWebRequest:HttpWebRequest) [Invoke-WebRequest]，WebException  
&nbsp; &nbsp; &nbsp; &nbsp; \+ FullyQualifiedErrorId : WebCmdletWebResponseException,Microsoft.PowerShell.Commands.InvokeWebRequestCommand

> - Those 2 Error happend, **surprisingly** beacause of I write a wrong port num , like below.
>  
> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;**8501:8501\-\-\>8501:8051** 💥💥💥💢💢💢(observe carefully here!!!)
> 
### 😂😂😂 I stuck here about 10 hours !!!  
(This is the reason why, I have this file.)





