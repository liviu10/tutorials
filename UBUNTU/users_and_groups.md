# Create and configured Ubuntu web server:

1. List users:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">      (show current user):</span> users
    <span style="color:white; font-weight:normal;">         (list all users):</span> cat /etc/passwd (getent passwd)</pre> 
    </span>

2. List groups:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">(show group current user):</span> groups username
    <span style="color:white; font-weight:normal;">        (list all groups):</span> cat /etc/group (getent group)</pre> 
    </span>

3. Create a new user:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">      (create a new user):</span> sudo useradd username
    <span style="color:white; font-weight:normal;">(new user + add to group):</span> sudo useradd -G groupname username</pre> 
    </span>

4. Change user password or set a password:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">       (set new password):</span> sudo passwd username</pre> 
    </span>

5. Add new group:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">     (create a new group):</span> sudo groupadd groupname</pre> 
    </span>

6. Add existing user to group:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">      (add user to group):</span> sudo usermod -a -G group username</pre> 
    </span>

7. Remove user from group:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;"> (remove user from group):</span> sudo gpasswd -d username group_to_remove_from</pre> 
    </span>

8. Change user primary group:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">     (user primary group):</span> sudo usermod -g group user</pre> 
    </span>

9. Delete groups:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">           (delete group):</span> sudo groupdel groupname</pre> 
    </span>

10. Delete user:

    <span style="color:red; font-weight:bold;">
        <pre>
    <span style="color:white; font-weight:normal;">           (delete group):</span> sudo userdel groupname</pre> 
    </span>