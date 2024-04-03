# Installing MongoDB on Windows

Download: https://www.mongodb.com/try/download/community

![alt text](image.png)

Hit Next

![alt text](image-1.png)

I accept should checked. Hit Next.

![alt text](image-2.png)

Hit Complete

![alt text](image-3.png)

Install MongoD as a Service checkbox
* Windows will automatically boot the MongoDB server
* We will keep this checked

Data and Log Directory
* Mongo manages data
* The data path "C:\Program Files\MongoDB\Server\7.0\data\" will be were the concrete DB will be written by default.
* Similar with logs "C:\Program Files\MongoDB\Server\7.0\log\"

![alt text](image-4.png)

MongoDB checkbox can be set and it will give you the GUI at the same time.

![alt text](image-5.png)

Approve with Admin privledges. Wait for it to install.
* Compass will take an additional few mins.

![alt text](image-6.png)

View this new service in Windows "Services" menu

![alt text](image-7.png)

From here you can right click start/stop whenever, but on system boot it will start automagically.

## CMD start stop

`net stop MongoDB` to stop Mongo
* Must be run in Admin mode cmdline

![alt text](image-8.png)

`net start MongoDB` to start Mongo again

![alt text](image-9.png)

Can use the services tool in Windows or the command line

We need to know the client. Go to where the server was installed.

From here the instructor double clicks on mongo.exe. I don't have this and it looks like he is sitting on 5.0 whereas I am on 7.0.

For me I had to install mongosh separately.

![alt text](image-10.png)

Hit Next

![alt text](image-12.png)

Uncheck the isntall just for you so its given PC wide. Hit Next "C:\Program Files\mongosh\"

![alt text](image-13.png)

Hit Finish

Now go to the install location "C:\Program Files\mongosh\""

![alt text](image-14.png)

Now use a basic command to view DB stats

`show dbs`

```
admin   0.000GB
config  0.000GB
local   0.000GB
```

Example output

![alt text](image-15.png)

That's all for now but we will use this more later!
