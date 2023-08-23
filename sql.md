SQL injection exists in the ibos office OA. Procedure

official website:http://www.ibos.com.cn/

version:4.5.5

Function point: Background Management = "Address Book Management =" Department and User Management = "Export user function

Route: r=dashboard/user/export&uid=X

The injection parameter: uid exists

The database name was successfully exploded using sqlmap
![WPS图片(2)](https://github.com/gatsby2003/cve/assets/135791683/a7edc1d8-5731-4fed-a58e-035b4867b826)
Invoke the exportUser() method through the actionExport() method

![WPS图片(3)](https://github.com/gatsby2003/cve/assets/135791683/82923431-1c29-4b44-969d-0ac4e73a948e)
The exportUser() method calls the fetchAllByUids() method of the model layer
![WPS图片(4)](https://github.com/gatsby2003/cve/assets/135791683/8edc388f-34f7-4a47-a7a0-be0664f21861)
Finally, the SQL statement is executed in the wrapUserInfo() method
![WPS图片(5)](https://github.com/gatsby2003/cve/assets/135791683/31a12a62-ea62-49b5-8687-d49232a46e77)
![WPS图片(6)](https://github.com/gatsby2003/cve/assets/135791683/c85d4b9b-f6be-4dcf-b0fe-80b7d17d695d)
![WPS图片(7)](https://github.com/gatsby2003/cve/assets/135791683/f88f9503-89b5-4b9d-80cf-d7d580f23742)
