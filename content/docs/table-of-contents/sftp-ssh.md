---
title: "SSH Keys for Secure FTP"
date: 2020-01-23T09:24:33-06:00
draft: true

#categories: [one]
#tags: [two, three, four]
---


# Generating a Secure Shell (SSH) Public/Private Key Pair

Several tools exist to generate SSH public/private key pairs. The following sections illustrate how to generate an SSH key pair on **UNIX, UNIX-like** and Windows platforms.




### Generating a SSH Key Pair on Windows Using the PuTTYgen Program

The PuTTYgen program is part of PuTTY, an open source networking client for the Windows platform. To generate an SSH key pair on Windows using the PuTTYgen program:

1. Download and install the full PuTTY package, or the individual PuTTYgen application. To download PuTTY or PuTTYgen, go to http://www.putty.org and click the download link.Step 1. Download and install the full PuTTY package, or the individual PuTTYgen application.

2. Run the PuTTYgen program. When the PuTTY Key Generator window is displayed; Set the "Type of key to generate" option to "RSA". In the "Number of bits in a generated key" box, enter 2048.

3. Click Generate to generate a public/private key pair. As the key is being generated, move the mouse around the blank area as directed.

4. Enter a passphrase for the private key in the **"Key passphrase"** box and reenter it in the **"Confirm passphrase"** box. While a passphrase is not required, you should specify one as a security measure to protect the private key from unauthorized use. When you specify a passphrase, a user must enter the passphrase every time the private key is used.

5. Delete the auto-generated text within the **"Key comment"** box, and replace it with your company assigned email address


6. Click **"Save Private Key"** to save the private key to a file. To adhere to file-naming conventions, you should give the private key file an extension of .ppk (PuTTY private key).

_The .ppk file extension indicates that the private key is in PuTTY’s proprietary format. You must use a key of this format when using PuTTY as the SSH client. It cannot be used with other SSH client tools._

7. Select all of the characters in the Public key for pasting into OpenSSH authorized_keys file box. Ensure that you have selected all the characters, not just the ones you can see in the narrow window.

Right click in the selected text and select Copy from the menu.



8. Open a text editor and paste the characters, just as you copied them. Do not insert any line breaks. Save the text file in the same folder where you saved the private key, using the .txt extension to indicate that the file contains a public key.

9. If you or others are going to use an SSH client that requires the OpenSSH format for private keys (such as the ssh utility on Linux), export the private key: On the Conversions menu, choose Export OpenSSH key. Save the private key in OpenSSH format in the same folder where you saved the private key in .ppk format, using an extension such as .openssh to indicate the file’s content.





### Generating an SSH Key Pair on UNIX and UNIX-Like Platforms Using the ssh-keygen Utility


1. Navigate to your home directory: **cd $HOME**

2. Run the ssh-keygen utility, substituting filename for the name of a file to store your private key and email_address for your email address: **ssh-keygen –b 2048 –t rsa –C email_address–f filename**. The ssh-keygen utility prompts you for a passphrase for the private key.

3. Enter a passphrase for the private key, or press Enter to create a private key without a passphrase: Enter passphrase (empty for no passphrase): passphrase While a passphrase is not required, you should specify one as a security measure to protect the private key from unauthorized

4. The ssh-keygen utility prompts you to enter the passphrase again. Enter the passphrase again, or press Enter again to continue creating a private key without a passphrase.

5. The ssh-keygen utility displays a message indicating that the private key has been saved as **filename** and the public key has been saved as **filename.pub** It also displays information about the key fingerprint and randomart image.



### File Access via FTP Client(s)

After your Customer Success Manager notifies you that your Public Key has been associated with the SFTP AIM Feed File directory, you will need to use an installed FTP client such as FileZilla or WinSCP to securely login to the directory.
+ FileZilla: https://filezilla-project.org
+ WinSCP: https://winscp.net/eng/download.php

Once your chosen application is installed:

#### Directions for FileZilla
1. Open the application From the top navigation, select Edit Click on "Settings" Click on "SFTP" Click "Add key file" Use Windows Explorer to navigate to the file that holds your previously saved Private Key (.ppk) file. Select the file and click "Open" Click OK

2. Enter **XXXXXXXX** in the "host" field

3. Enter the **DMD supplied username + property name**. in the "username" field Example: dmd-username.dmd-property

4. Enter the passphrase/password you generated in the "key pass phrase" (step 3 of "Generating an SSH Key Pair on UNIX and UNIX-Like Platforms Using the ssh-keygen Utility" or step 4 of "Generating an SSH Key Pair on Windows Using the PuTTYgen Program")

5. In the "port" field, enter **22**

6. Click "connect"

7. You will be logged into the directory containing the AIM Feed Files for the selected property. Drag the file to the directory on your local machine where you would like to store the file.

#### Directions for WinSCP
1. Open the application From the Login window click on the "Advanced" drop down button Click "Advanced" In the Advanced Site Settings window, clicks "Authentication" under "SSH" In the "Private key file" field click the button on the far right Navigate to the location of your saved Private Key File, select the file and click "Open" Click "OK" and you will be returned to the Login window

2. Enter **XXXXXXXX** in the "host" field

3. In the "port" field, enter 22

4. Enter the DMD supplied username + property name. in the "username" field Example: dmd-username.dmd-property

5. Do Not enter a password

6. Click Login You may see an advisory window – Click OK

7. Enter the passphrase/password you generated in the "key pass phrase" (step 3 of "Generating an SSH Key Pair on UNIX and UNIX-Like Platforms Using the ssh-keygen Utility" or step 4 of "Generating an SSH Key Pair on Windows Using the PuTTYgen Program") in the "key passphrase" window

8. Click "OK"

9. You will be logged into the directory containing the AIM Feed Files for the selected property. Drag the file to the directory on your local machine where you would like to store the file.





---
Author: M Miryani |
---
Ref: http://docs.dmdconnects.com/resources/aim-feed-ssh-key-generation
---
