Curl scripts to automate user/group management in Adobe AEM
-
######Create User
<sub>
curl -u "*adminusername*:*password*" --proxy *your-proxy*:*port*  -FcreateUser= -FauthorizableId=*new-users-id* -Frep:password=*new-users-password* http://*server-name*:4502/libs/granite/security/post/authorizables
</sub>
-
######Create Group
<sub>
curl -u "*adminusername*:*password*" --proxy *your-proxy*:*port*  -FcreateGroup="*new group name*" -FauthorizableId=*new-group-id* http://*server-name*:4502/libs/granite/security/post/authorizables
</sub>
-
######Create User as member of group(s)
<sub>
curl -u "*adminusername*:*password*" --proxy *your-proxy*:*port*  -FcreateUser= -FauthorizableId=*new-users-id* -Frep:password=*new-users-password* -Fmembership=everyone -Fmembership=content-authors -Fmembership=workflow-users http://*server-name*:4502/libs/granite/security/post/authorizables
</sub>
-
######Add User to a group
<sub>
curl -u "*adminusername*:*password*" --proxy *your-proxy*:*port*  -FaddMembers=*user-to-be-added*  http://*server-name*:4502/home/groups/*path/to/target/group*.rw.html
</sub>
-
######Delete a User
<sub>
curl -u "*adminusername*:*password*" --proxy *your-proxy*:*port*  -FdeleteAuthorizable=  http://*server-name*:4502/home/users/*path/to/user*
</sub>
-
######Delete a Group
<sub>
curl -u "*adminusername*:*password*" --proxy *your-proxy*:*port*  -FdeleteAuthorizable=  http://*server-name*:4502/home/groups/*path/to/group*
</sub>
-
######Remove User from a group
<sub>
curl -u "*adminusername*:*password*" --proxy *your-proxy*:*port*  -FremoveMembers=*user-to-be-removed*  http://*server-name*:4502/home/groups/*path/to/group*.rw.html
</sub>
-
######Change Password
<sub>
curl -u "*username*:*password*" --proxy *your-proxy*:*port*  -Frep:password=*new-password*  http://*server-name*:4502/home/users/*path/to/user*.rw.html
</sub>

