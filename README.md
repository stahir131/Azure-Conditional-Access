<p align="center"><b>Conditional Access</b></p>

Configuring a Conditional Access policy for Multi-Factor Authentication (MFA) in Microsoft Entra ID (formerly Azure Active Directory) enables an organization to enforce additional security by requiring users to complete a second verification step during sign-in. Here’s a step-by-step guide:<br />
 <br />I have created a group: Enforce_2FA<br />

<b>Note: You’ll need to disable Security Default before creating any policy with Conditional access.</b>

**Step 1: Access Microsoft Entra ID (Azure AD) Portal<br />**
Go to Microsoft Entra Admin Center and sign in with global administrator credentials.<br />
In the left-hand menu, select Security > Conditional Access.


**Step 2: Create a New Conditional Access Policy**<br />
In the Conditional Access section, click on + New policy to create a new policy.<br />
Name :**Require MFA for All Users**.<br />
Under Users: Under Include<br />
Select <b>users and groups</b>
Add Enforce_2FA group <br />
Under Exclude> You can exclude any group out of this policy<br />
![image](https://github.com/user-attachments/assets/50fbd691-ddce-4ffb-afc0-be7b5216d442)
<br />

**Step 3: Target resources:** Include> All cloud apps, you can exclude any apps you want<br />
![image](https://github.com/user-attachments/assets/a23fc9cd-8c38-4f69-a104-20c2bf48cf30)

<b>Step 4: Network</b>: Control user access based on their network or physical location.

<b>Step 5: Conditions</b>: Control access based on signals from conditions like risk, device platform, location, client apps, or device state. This covers the device platform eg iOS, the locations determined by IP or GPS, the client apps the user is signing in from.

**Step 6: Under Access control:** Select Grant access and check “Require multi factor authentication” , click <b>Select.</b>
![image](https://github.com/user-attachments/assets/5170dcd3-8626-4077-8e81-dfad1afb2ea4)

Review the settings to ensure accuracy, and then click Create to apply the policy.<br />
<b>Only toggle Enable policy to On when ready to deploy.</b><br />
<b>Create.</b><br />
The policy was tested and works. 


