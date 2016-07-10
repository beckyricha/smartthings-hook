Installation

Note: HookDevices is a SmartThings device handler, which works only for toggle on/off devices using hook home automation (for more info go to gethook.io). This is a "quick and dirty" approach.  It does not poll for hook devices or maintain updates.  You will have to install each device manually, as well as any changes you make to it.  You will also need ot update the device handler if your hook token changes.  Installing custom device is a two-step process -- first, you need to install and self-publish the SmartDevice Type, then you need to create an instance of the new SmartDevice. Both steps must be performed in the SmartThings Web-based IDE.

1. Installing Hook SmartDevice Type

    Open SmartThings IDE in your web browser and log into your account.
    Click on the "My Device Types" section in the navigation bar (or open the SmartDevices page).
    On the "<Your Name>'s Device Types" page, click on the "+ New SmartDevice" button on the right.
    On the "New SmartDevice" page, click the tab that says "from code."
    Copy the Hook source code from GitHub and paste it into the IDE editor window (see previous step). Make sure you completely overwrite contents of the editor window with the source code copied from the GitHub.
    Scroll down to the line (should be line 47) that reads: 
    uri: "https://api.gethook.io/v1/device/trigger/${device.deviceNetworkId}/${toggle}/?token=yourhooktoken"
    
    Replace yourhooktoken with your hook token number (this can be obtained by going to your hook web account, going to your devices page clicking the arrow to the right of any device, and selecting "IFTTT."  The long number that appears after "token=" is your hook token.  While you are there, you may also want to copy and save the number that appears after "trigger/" and before the next "/" as you will need this for each device you want to add.
    Click the blue "Save" button above the editor window.
    Click the "Publish" button next to it and select "For Me". You have now self-published your smart device handler.

2. Installing a Hook switch SmartDevice

    In the SmartThings IDE, click on the "My Devices" section (or open the Device List page).
    On the "Device List" page, click on the "+ New Device" button on the right.
    On the "Create Device" page, enter device name in the mandatory "Name" field. You can use any name here, for example "Lamp".
    Optionally, enter device label in the "Label" field. This is the actual label that will displayed in the SmartThings mobile app.
    Fill in the mandatory "Device Network Id" filed. This is the number assigned by hok to your device.  Using the sam steps as above where you obtained your hook token, this is hte other number that appears after "trigger/" and before the other "/"  do not add any quotes or toher things, just this number.
    In the mandatory "Type" field, select "Hook" from the drop-down list.
    In the mandatory "Version" field, select "Published" from the drop-down list.
    In the "Location" field, select location where you want to install new device.
    In the "Hub" filed, select the name of your SmartThings hub.
    Click the blue "Create" button at the bottom of the page.

3. Refresh Device List in SmartThings Mobile App

    Open the SmartThings app on your mobile device, go to the Dashboard and log out of your SmartThings account.
    Exit and restart the SmartThings mobile app.
    Log back in into your SmartThings account. A new RadioThermostat device should now appear on the "Things" page.

Now the hook device should look just like any other smartthings switches you have.  Note that hook does nto send status info, so your switch may not keep up properly wiht on/off status. If a device is already in the only state you can switch to, just press it twice.  No harm.  You can also integrate your device wiht Alexa, but may need to disconnect and reconnect smartthing access, as each device needs to be authorized for Alexa during that process.  

License

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see http://www.gnu.org/licenses/.
