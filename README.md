Project description
Through Linux command-line tools, I audited and secured file and directory permissions by identifying unnecessary access and applying the correct permission settings. I used `ls -la` to inspect ownership and existing permissions, then used `chmod` to remove unauthorized write and execute permissions. I restricted other users from modifying `project_k.txt`, secured the hidden `.project_x.txt` file by limiting it to the required read permissions, and restricted group access to the `drafts` directory. After making each change, I verified the updated permissions to ensure the security requirements were met. Overall, I used Linux commands to strengthen access control, reduce unnecessary privileges, and apply the principle of least privilege.

Check file and directory details
I used the ls -la command to display all files, including hidden files, along with their detailed information.
Describe the permissions string
The file permissions are shown as a 10-character string, for example drwxr-xr-x. The first character, d, indicates that the item is a directory. The letters r, w, and x represent read, write, and execute permissions, while a hyphen (-) means that permission is not granted. The next nine characters are divided into three groups of three: the first group represents the user (owner), the second represents the group, and the last represents others.
Change file permissions
Since the organization's policy does not allow others to have write access to any file, I found that project_k.txt had write permission for others. To remove this permission and comply with the policy, I used the command chmod o-w project_k.txt.
Change file permissions on a hidden file
The research team archived a hidden file named .project_x.txt, which should not have write permission. According to the required permissions, only the user and group should have read permission, while write permission should be removed. To apply the correct permissions and ensure the file met the required security policy, I used the command chmod u=r,g=r .project_x.txt.
Change directory permissions
The projects directory belongs to the researcher2 user, and only researcher2 should have access to the drafts directory and its contents. To remove access permissions from the group and ensure that only the owner can access the directory, I used the command chmod g-x drafts to remove the group's execute permission.
