OpenPilot recognizes which car is connected by comparing the CAN signals read to lists in... /data/openpilot/selfdrive/car/ car make/values.py
Currently, different trim packages of the same model often have different fingerprints, which can require one to create their own fingerprint if Comma hasn't already included it.

You can use [https://opc.ai/workbench Workbench] for finding your EON on your network, connecting to it via SSH, and grabbing your vehicles fingerprint while EON is connected to your vehicle.

This procedure does NOT teach you how to install OpenPilot, SSH, use VIM, etc.


1. Turn off car, connect Panda to car (normally via Giraffe), and connect Panda to EON running OpenPilot.

2. Set the Giraffe switches so the stock system is enabled. For this procedure you want to collect the messages sent by the stock system, not openpilot.

3. Run these commands in 2 separate sessions (SSH'd into EON)...
<pre>
/data/openpilot/selfdrive/boardd/boardd
cd /data/openpilot/selfdrive && PYTHONPATH=/data/openpilot PREPAREONLY=1 /data/openpilot/selfdrive/debug/get_fingerprint.py
</pre>

4. Turn on the car's ignition, and wait up to ~20 seconds to ensure all the appropriate DBC messages are seen, like this...
<pre>
number of messages: 107
fingerprint 36L: 8, 37L: 8, 166L: 8, 170L: 8, 180L: 8, 295L: 8, 296L: 8, 426L: 6, 452L: 8, 466L: 8, 467L: 8, 550L: 8, 552L: 4, 560L: 7, 562L: 6, 581L: 5, 608L: 8, 610L: 8, 614L: 8, 643L: 7, 658L: 8, 713L: 8, 740L: 5, 742L: 8, 743L: 8, 800L: 8, 810L: 2, 814L: 8, 824L: 2, 829L: 2, 830L: 7, 835L: 8, 836L: 8, 863L: 8, 869L: 7, 870L: 7, 871L: 2, 898L: 8, 900L: 6, 902L: 6, 905L: 8, 913L: 8, 918L: 8, 921L: 8, 933L: 8, 944L: 8, 945L: 8, 950L: 8, 951L: 8, 953L: 8, 955L: 8, 956L: 8, 971L: 7, 974L: 8, 975L: 5, 993L: 8, 998L: 5, 999L: 7, 1000L: 8, 1001L: 8, 1014L: 8, 1017L: 8, 1020L: 8, 1041L: 8, 1042L: 8, 1044L: 8, 1056L: 8, 1057L: 8, 1059L: 1, 1071L: 8, 1076L: 8, 1077L: 8, 1082L: 8, 1083L: 8, 1084L: 8, 1085L: 8, 1086L: 8, 1114L: 8, 1132L: 8, 1161L: 8, 1162L: 8, 1163L: 8, 1164L: 8, 1165L: 8, 1166L: 8, 1167L: 8, 1175L: 8, 1227L: 8, 1228L: 8, 1235L: 8, 1237L: 8, 1279L: 8, 1552L: 8, 1553L: 8, 1556L: 8, 1557L: 8, 1568L: 8, 1570L: 8, 1571L: 8, 1572L: 8, 1595L: 8, 1777L: 8, 1779L: 8, 1904L: 8, 1912L: 8, 1990L: 8, 1998L: 8
</pre>

5. Turn on and off the car few times to make sure all messages are received (some messages are only sent on start).

6. <CTRL> + 'C' to break out of the process.

7. Copy the DBC messages obtained from step 3 into the "FINGERPRINTS" section of... /data/openpilot/selfdrive/car/{car make}/values.py [Create new sub-section for car, or overwrite pre-existing fingerprint of similar car.]

8. Turn off car's ignition, then powercycle EON.
<pre>
reboot
</pre>
