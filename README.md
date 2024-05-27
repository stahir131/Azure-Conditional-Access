<p align="center"><b>Conditional Access</b></p>

Setting up Conditional Access policy to enforce Multi Factor Authentication. There are 100's of policies that can be enforced here.<\br>
 Enforcing 2FA on some users and excluding some users based on the group they belong to.</br>
I have created 2 groups: Enforce_2FA and Exclude_2FA groups</br>
- Enforce_2FA contains user1 and user2</br>
- Exclude_2FA contains only user3</br>

<b>Note: You’ll need to disable Security Default before creating any policy with Conditional access.</b>

Go to EntraID admin portal

Select <b>Security</b> then
<b>Policy</b>

Select <b>Create New Policy</b>

Create Name: Multifactor_policy

Under Users: Under Include

Select <b>users and groups</b>

Add Enforce_2FA group </br>
Under Exclude> Add “Exclude_2FA group”
Target resources: Include> All cloud apps, you can exclude any apps you want

<b>Network</b>: Control user access based on their network or physical location.

<b>Conditions</b>: Control access based on signals from conditions like risk, device platform, location, client apps, or device state. This covers the device platform eg iOS, the locations determined by IP or GPS, the client apps the user is signing in from.

Under Access control: Select Grant access and check “Require multi factor authentication” , click <b>Select.</b>

<b>Only toggle Enable policy to On when ready to deploy.

Create.</b>

The policy was tested and works. 

The user1 and user2 in the Enforce_2FA group got prompted to provide 2FA either with an MFA app or via texting their phone while the user3 in my Exclude_2FA group was able to sign in directly.

Note: Each user has the ability to choose what method to use for authentication between downloading the app or just receiving text. This can be modified if user sign using the web app > Under user Avatar > View Account

