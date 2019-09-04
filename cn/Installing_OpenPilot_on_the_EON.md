== Installing ==
=== Quick Guide ===
* Navigate to the chffrplus settings and select Uninstall
* After you reboot, configure networking (either with SIM or WiFi)
* NEOS will ask for an install URL; enter https://openpilot.comma.ai
* The phone will begin the installation which will reboot and take 10 to 30 minutes
** Don't worry if the screen is black for a long time, or has the loading spinner for a long time. Just be patient.
** However, if the EON boots and does not have network access, it can and does hang indefinitely until the network comes back!

'''Congratulations, you have openpilot on your EON!'''

=== Troubleshooting & Tips ===

'''''I can't see the whole keyboard when trying to sign into openpilot'''''

There is currently a bug that only displays part of the keyboard when you try to sign into openpilot.

To fix this <font color=red>reboot</font> the EON.

'''''If you don't have an active SIM installed'''''

You should manually set the EON's Date, Time, and Zone in Settings to have timestamps on your data and videos aligned to your clock.


=== Other Guides & Helpful Links ===

'''[https://medium.com/@jfrux/comma-eon-initial-setup-with-openpilot-2b5ea58354a Comma EON: Initial Setup with openpilot]''' by [https://medium.com/@jfrux/ @jfrux]

An in depth guide with visuals on setting up your new EON with openpilot.

----

'''[VIDEO] [https://www.youtube.com/watch?v=67ToRRXrwDI  How to Install openpilot on the EON Dashcam DevKit]''' by [https://www.youtube.com/channel/UCeHc0xNYWSSoS1aBZ_xmDbw @VirtuallyChris]

== Reinstalling openpilot ==

* Reboot the EON and hold the volume UP and power buttons. For EON's on old NEOS, hold the volume DOWN and power buttons.
* The phone should show the comma logo and boot into the cyanogenmod recovery screen.
* Click "factory reset" then "full factory reset" and confirm.
* Power off the phone and boot it back up
* Then once again follow the steps listed above, minus the Chffrplus step


See [[Installing Giraffe]] and [[Installing EON]] for information on installing the hardware into your car
See [[Configuring OpenPilot]] for information on how to get openpilot talking to your car.

See [[First OpenPilot Drive]] for next steps.

Visit #openpilot on comma.slack.com and say hello

== Guides & Useful Links ==
'''[VIDEO] [https://www.youtube.com/watch?v=67ToRRXrwDI  How to Install openpilot on the EON Dashcam DevKit]''' by [https://www.youtube.com/channel/UCeHc0xNYWSSoS1aBZ_xmDbw @VirtuallyChris]

An excellent visual guide to installing openpilot on your EON Dashcam DevKit.

----

'''[https://medium.com/@jfrux/comma-eon-initial-setup-with-openpilot-2b5ea58354a Comma EON: Initial Setup with openpilot]''' by [https://medium.com/@jfrux @jfrux]

An in depth guide to walk you through setting up your new EON with openpilot

----

'''[https://medium.com/@jfrux/comma-eon-getting-connected-with-ssh-3ed6136e4a75 Comma EON: Getting Connected with SSH]''' by [https://medium.com/@jfrux @jfrux]

A useful guide if you want to learn how to use SSH to connect to your EON for advanced configuration or maintenance reasons.  
It is friendly to Windows, Mac, and Linux.

----

'''[https://medium.com/@jfrux/comma-eon-getting-connected-with-ssh-3ed6136e4a75 Comma EON: Getting Connected with SSH]''' by [https://medium.com/@jfrux @jfrux]

Learn how to use SSH to connect to your EON for advanced configuration and maintenance purposes.

----

'''[https://medium.com/@jfrux/comma-eon-installing-tools-for-accessing-eon-via-ssh-on-windows-d8eb1ba7e7e5 Comma EON: Installing Tools for Accessing EON via SSH on Windows 10]''' by [https://medium.com/@jfrux @jfrux]

Learn how to install special tools to your Windows 10 machine to connect to your EON for advanced configuration and maintenance purposes.  
Mac / Linux come standard with these tools.

----

'''[https://medium.com/@jfrux/comma-eon-installing-a-fork-of-openpilot-5c2b5c134b4b Comma EON: Installing a Fork of openpilot]''' by [https://medium.com/@jfrux @jfrux]

Learn how to install custom versions of openpilot tailored to your requirements.
