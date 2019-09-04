## 快速入门

### 资料网站：

- [Comma ai](http://comma.ai/)
- [Comma wiki](https://community.comma.ai/wiki)
- [Comma ai github](https://github.com/commaai)
- [Commaai archive Youtube](https://www.youtube.com/channel/UCwgKmJM4ZJQRJ-U5NjvR2dg)


### 新手引导

- [安装 Giraffe](cn/Installing_Giraffe.md)
- [安装 EON](cn/Installing_EON.md)
- [在 EON 上运行 ChffrPlus](cn/Running_ChffrPlus_on_the_EON.md)
- [Installing OpenPilot on the
    EON](Installing_OpenPilot_on_the_EON "wikilink")
- [Configuring OpenPilot](Configuring_OpenPilot "wikilink")
- [First OpenPilot Drive](First_OpenPilot_Drive "wikilink")
- [Hardware Guide](Hardware_Guide "wikilink")
- [Software Guide](Software_Guide "wikilink")
- [FAQ](cn/FAQ.md)

### 车辆

- [Candidate Vehicles](Candidate_Vehicles "wikilink")
- [Working
    Vehicles](https://github.com/commaai/openpilot#supported-cars)
- [Vehicle Makes](:Category:Vehicle_Makes "wikilink")
- If your car isn\'t supported yet, try putting up some cash:
- [Bounties](Bounties "wikilink")


### 故障排除

参考以下链接内容排除 Panda 和 EON 的问题。

- [Panda](cn/Panda.md)
- [EON](cn/EON.md)
- [FAQ](cn/FAQ.md)

Development
-----------

- [Panda Firmware](Panda_Firmware "wikilink")
- [Driving Intermediate Layer](Driving_Intermediate_Layer "wikilink")
- [Creating Fingerprints](Creating_Fingerprints "wikilink")
- [Getting Internet at hotels or places with web
    authentication](Getting_Internet_at_hotels_or_places_with_web_authentication "wikilink")

Community
---------

Comma has a vibrant community working on new ports and features for
Comma.

Check out the [Discord server](https://discord.comma.ai/).

- [How to help](How_to_help "wikilink")

### Community initiatives {#community_initiatives}

[The Openpilot Community](https://opc.ai/)

It is a community supported initiative with a special database website
located at <https://opc.ai/> which features an up-to-date list of
compatible vehicles, as well as vehicles that the community is working
on porting. The website also includes Guides, Videos, and detailed
information about each vehicle year make and model.

You may also want to subscribe to their [subreddit:
r/openpilotcommunity](https://reddit.com/r/openpilotcommunity)

Feedback/Feature requests {#feedbackfeature_requests}
-------------------------

openpilot did something wrong or unexpected? Report the event in the
[openpilot Events](openpilot_Events "wikilink").

Want to suggest a feature? Go to [GitHub Issues
Tracker](https://github.com/commaai/openpilot/issues) and make your
suggestions.

Glossary of terminology {#glossary_of_terminology}
-----------------------

  Term                                  Alternate Names      Links                                                                                                                                                                            Definition
  ------------------------------------- -------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Adaptive Cruise Control               ACC                  [wikipedia](https://en.wikipedia.org/wiki/Adaptive_cruise_control)                                                                                                               An available cruise control system for road vehicles that automatically adjusts the vehicle speed to maintain a safe distance from vehicles ahead. As of 2019, it also called by 20 unique names that describe that basic functionality. This is also known as Dynamic cruise control.
  Advance-Angle                                              [discord](https://discordapp.com/channels/469524606043160576/538741329799413760/615266067002032158)                                                                              A control algorithm that uses the [EPS](#EPS "wikilink") motor torque to calculate a much more accurate steering angle, similar to LQR.
  Advanced Driver-Assistance Systems    ADAS                 [wikipedia](https://en.wikipedia.org/wiki/Advanced_driver-assistance_systems)                                                                                                    Electronic systems that aid a vehicle driver while driving.
  Automatic Lane Change Assistance      ALCA                                                                                                                                                                                                  Although implemented in some custom forks, considered a safety issue, and not endorsed by Comma.ai.
  Automatic High Beams                  AHB                                                                                                                                                                                                   A safety system designed to help the driver have better visibility at night -- while reducing glare for other drivers.
  Bosch                                                      [wikipedia](https://en.wikipedia.org/wiki/Robert_Bosch_GmbH#Mobility_Solutions)                                                                                                  A manufacturer of auto parts used by [OEMs](#OEM "wikilink"). In the context of OP it refers to a particular type of driver assistance hardware that is found in vehicles such as the 2017+ Honda CR-V.
  Controller Area Network               CAN, CAN bus         [wikipedia](https://en.wikipedia.org/wiki/CAN_bus)                                                                                                                               A message-based protocol that provides a standardized way for [ECUs](#ECU "wikilink") to communicate with each other.
  Chffr                                                                                                                                                                                                                                       A free app that turns your cell phone into a dashcam, discontinued mid-2019.
  Chffrplus                                                  \[<https://>`{{SERVERNAME}}`{=mediawiki}/Running\_ChffrPlus\_on\_the\_EON guide\]                                                                                                Pre-installed app on the [EON DevKit](#EON "wikilink") that turns the it into a dashcam.
  Comma.ai                                                   [website](http://comma.ai)                                                                                                                                                       The company behind openpilot
  Comma Connect                                                                                                                                                                                                                               A mobile app for [Android](https://play.google.com/store/apps/details?id=ai.comma.connect&hl=en_US) and [iOS](https://apps.apple.com/us/app/comma-connect/id1456551889)
  Comma Pedal                                                \[<https://>`{{SERVERNAME}}`{=mediawiki}/Comma\_Pedal wikipedia\]                                                                                                                A device that provides stop-and-go capability on cars that don\'t currently support it. This device is not sold by Comma.ai (not officially supported by them), but supported in OpenPilot.
  Comma API                                                  [docs](https://api.comma.ai/#comma-api-spec)                                                                                                                                     
  Comma Points                                               \[<https://>`{{SERVERNAME}}`{=mediawiki}/FAQ\#commapoints wikipedia\]                                                                                                            Awarded for various activities you perform on the platform.
  Comma Power                                                [buy](https://comma.ai/shop/products/power)                                                                                                                                      Use your car\'s [OBD-II](#OBD2 "wikilink") port to power your Toyota, Bosch, or FCA Giraffe
  Comma Prime                           Prime                [buy](https://comma.ai/shop/products/comma-prime-sim-card)                                                                                                                       A subscription service from comma.ai offering a specific list of benefits.
  DRCC                                                       Dynamic Radar Cruise Control                                                                                                                                                     A cruise control system that uses a front grille-mounted radar and a forward-facing camera that is designed to detect a vehicle in front of you and automatically adjust the vehicle\'s speed to help maintain a pre-set distance behind a vehicle ahead.
  Electronic Control Unit               ECU                  [wikipedia](https://en.wikipedia.org/wiki/Electronic_control_unit)                                                                                                               Any embedded system in automotive electronics that controls one or more of the electrical systems or subsystems in a vehicle.
  EON DevKit                            EON, EON Gold        [buy](https://comma.ai/shop/products/eon-gold-dashcam-devkit) \[<https://>`{{SERVERNAME}}`{=mediawiki}/Installing\_EON install\]                                                 A smartphone running a customized version of Android and a custom case with additional cooling. This device runs the OpenPilot software.
  Electric Power Steering               EPS, EPAS            [wikipedia](https://en.wikipedia.org/wiki/Power_steering#Electric_systems)                                                                                                       Uses an electric motor to assist the driver of a vehicle. Sensors detect the position and torque of the steering column, and a computer module applies assistive torque via the motor, which connects to either the steering gear or steering column.
  fingerprint                                                [discord](https://discordapp.com/channels/469524606043160576/524327905937850394/597941450407149599) \[<https://>`{{SERVERNAME}}`{=mediawiki}/Creating\_Fingerprints creating\]   A list of [CAN bus](#CAN "wikilink") signals unique to a particular vehicle. Allows OpenPilot to recognize which car it is connected to.
  firmware                                                   [wikipedia](https://en.wikipedia.org/wiki/Firmware)                                                                                                                              Low-level software that runs directly on hardware such as the Panda.
  flashing                                                   [wikipedia](https://en.wikipedia.org/wiki/Firmware#Flashing)                                                                                                                     A method of writing firmware to a hardware device.
  fork                                  custom fork          [wikipedia](https://en.wikipedia.org/wiki/Fork_(software_development))                                                                                                           In software engineering, a project fork happens when developers take a copy of source code from one software package and start independent development on it, creating a distinct and separate piece of software.
  FrEON                                 OpenFrEON            [github](https://github.com/ch4se/OpenFrEON)                                                                                                                                     \"Free EON\"\... an open source variant of the EON case. The repository contains files that can be used for 3D printing a case. Developed by \@Chase\#7213
  Giraffe connector                     Giraffe              [buy](https://comma.ai/shop/products/giraffe) \[<https://>`{{SERVERNAME}}`{=mediawiki}/Installing\_Giraffe install\]                                                             An adapter board that lets you read buses that aren\'t exposed on the main OBD-II connector, with variants for different vehicle makes/models.
  General Motors Local Area Network     GMLAN                [wikipedia](https://en.wikipedia.org/wiki/General_Motors_Local_Area_Network)                                                                                                     A superset of [CAN Bus](#CAN "wikilink") bus developed by General Motors.
  heat sink                             heatsink             [wikipedia](https://en.wikipedia.org/wiki/Heat_sink)                                                                                                                             A passive cooling device.
  hugging                                                                                                                                                                                                                                     An undesired behavior where the vehicle drives too closely to one side of the lane.
  INDI                                                                                                                                                                                                                                        A control algorithm like PIF, PID, and LQR.
  Lane Departure Alert                  LDA                                                                                                                                                                                                   Uses an in-vehicle camera to detect lane departure when traveling on relatively straight roads with clear lane markings, and only alerts the driver.
  LeEco Le Pro 3                        Lepro, LeEco, x727   [specs](https://www.gsmarena.com/leeco_le_pro3-8344.php)                                                                                                                         The current phone used in the EON. Specifically the x727 model
  LiveParameters                                                                                                                                                                                                                              A continually updated file (ie. \"Live\")that stores learned calibration data for the vehicle.
  Lane Keeping Assist                   LKAS                 [wikipedia](https://en.wikipedia.org/wiki/Lane_departure_warning_system#Lane_keeping)                                                                                            Technology that automatically takes steps to ensure the vehicle stays in its lane.
  LQR                                                                                                                                                                                                                                         A control algorithm like INDI, PIF, and PID.
  Machine learning model                model                [wikipedia](https://en.wikipedia.org/wiki/Machine_learning)                                                                                                                      
  Nidec                                                                                                                                                                                                                                       A manufacturer of auto parts used by [OEMs](#OEM "wikilink"). In the context of OP it refers to a particular type of driver assistance hardware that is found in vehicles such as the 2016+ Honda Pilot.
  OBD-II                                                     [wikipedia](https://en.wikipedia.org/wiki/On-board_diagnostics#OBD-II)                                                                                                           On-Board Diagnostics Connector
  Original Equipment Manufacturer       OEM                  [wikipedia](https://en.wikipedia.org/wiki/Original_equipment_manufacturer#Automotive_parts)                                                                                      When referring to auto parts, OEM refers to the manufacturer of the original equipment, that is, the parts assembled and installed during the construction of a new vehicle.
  OnePlus 3T                            OP3T                 [wikipedia](https://en.wikipedia.org/wiki/OnePlus_3T)[specs](https://www.gsmarena.com/oneplus_3t-8416.php)                                                                       The phone used in the previous generation EON. It was discontinued due to a lack of supply. [1](https://forums.oneplus.com/threads/a3000-or-a3010-in-the-u-s.530600/) Known model numbers: A3000(US version) A3010(Asian version)
  OpenPilot                             OP                   [wikipedia](https://en.wikipedia.org/wiki/Openpilot)                                                                                                                             
  OpenStreetMap                         OSM                  [wikipedia](https://en.wikipedia.org/wiki/OpenStreetMap)                                                                                                                         An open-source project who\'s aim is to create a free editable map of the world.
  Open-source software                  OSS                  [wikipedia](https://en.wikipedia.org/wiki/Open-source_software)                                                                                                                  A type of computer software in which source code is released under a license in which the copyright holder grants users the rights to study, change, and distribute the software to anyone and for any purpose.
  Panda OBD-II Interface                Panda                [buy](https://comma.ai/shop/products/panda-obd-ii-dongle)                                                                                                                        A CAN-Bus to USB adapter. Available in 2 variants: white (incl. WiFi) / grey (incl. high precision GPS).
  Panda Paw                             Paw                  [buy](https://comma.ai/shop/products/panda-paw)                                                                                                                                  A device to help you unbrick a panda.
  PID                                                        [wikipedia](https://en.wikipedia.org/wiki/PID_controller)                                                                                                                        A control algorithm like INDI, LQR, and PIF.
  PIF                                                                                                                                                                                                                                         A control algorithm like INDI, LQR, and PID\... where \'F\' refers to \'FeedForward\'.
  ping pong                             ping ponging                                                                                                                                                                                          An undesired behavior where the vehicle sways from one side of the lane to the other repeatedly. The desired behavior is to stay in the center of the lane.
  Pre-Collision System                  PCS                                                                                                                                                                                                   Uses an integrated forward-facing camera and grille mounted radar system designed to help mitigate or avoid a potential collision with another vehicle or pedestrian.
  Proxy Panda                                                                                                                                                                                                                                 
  Stop-and-Go                           SnG                                                                                                                                                                                                   
  Snapdragon Neural Processing Engine   SNPE                 [dev info](https://developer.qualcomm.com/software/qualcomm-neural-processing-sdk)                                                                                               A Qualcomm Snapdragon software accelerated runtime for the execution of deep neural networks.
  STL file                                                   [wikipedia](https://en.wikipedia.org/wiki/STL_(file_format)#Use_in_3D_printing)                                                                                                  A file that describes a 3D object. In the case of OP, these kind of files are used when 3D printing the [FrEON](#OpenFrEON "wikilink") case, mounts, etc.
  TensorFlow                            TF                   [wikipedia](https://en.wikipedia.org/wiki/TensorFlow)                                                                                                                            An open-source machine learning library
  Toyota Safety Sense 2                 TSS-2                [info](https://www.toyota.com/content/ebrochure/CFA_TSS_2.pdf)                                                                                                                   TSS 2.0 builds on the previous TSS-C and TSS-P suites, and consists of six active safety and driver assistance systems: PCS, DRCC, LDA, AHB, RSA, and LTA.
  Toyota Safety Sense C                 TSS-C                [info](https://www.toyota.com/content/ebrochure/CFA_TSS_C.pdf)                                                                                                                   An advanced active safety package for compact vehicles, and consists of six active safety and driver assistance systems: PCS, DRCC, LDA, and AHB.
  Toyota Safety Sense P                 TSS-P                [info](https://www.toyota.com/content/ebrochure/CFA_TSS_P.pdf)                                                                                                                   An advanced active safety package for mid-size and large vehicles, and consists of six active safety and driver assistance systems: PCS, LDA, and AHB.
  Zorro Steering Sensor                 ZSS                  [github](https://github.com/zorrobyte/betterToyotaAngleSensorForOP)                                                                                                              A DIY angle sensor to replace the inferior one used in TSS-P Toyotas (notably problematic with Prius and Prius Prime)

(You must have at least 500 [<span style="color:goldenrod">comma
points</span>](FAQ#commapoints "wikilink") to edit this wiki.)
