# Intune IOS Application
## Auto Enroll on Launch 
#### This method allows the Intune SDK to handle all authentication with MSAL and enrollment before your app finishes launching. <br> ref:
<br>
> [!NOTE]
> : Your application will always require a App Protection Policy when using this method.
<br> Simply set the two settings to 'Yes' in the IntuneMaMSetting dictionary in the app's Info.plist.
<br>
Ref :https://learn.microsoft.com/en-us/mem/intune/developer/app-sdk-ios-phase3#let-intune-handle-authentication-and-enrollment-at-launch
<br>
<br>
<table aria-label="Table 3" class="table table-sm margin-top-none">
<thead>
<tr>
<th>Setting</th>
<th>Type</th>
<th>Definition</th>
</tr>
</thead>
<tbody>
<tr>
<td>AutoEnrollOnLaunch</td>
<td>Boolean</td>
<td>Specifies whether the app should attempt to automatically enroll on launch if an existing managed identity is detected and it has not yet done so. Defaults to NO. <br><br> Note: If no managed identity is found or no valid token for the identity is available in the ADAL/MSAL cache, the enrollment attempt will silently fail without prompting for credentials, unless the app has also set MAMPolicyRequired to YES.</td>
</tr>
<tr>
<td>MAMPolicyRequired</td>
<td>Boolean</td>
<td>Specifies whether the app will be blocked from starting if the app doesn't have an Intune app protection policy. Defaults to NO. <br><br> Note: Apps can't be submitted to the App Store with MAMPolicyRequired set to YES. When setting MAMPolicyRequired to YES, AutoEnrollOnLaunch should also be set to YES.</td>
</tr>
</tbody>
</table>
