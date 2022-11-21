# What the hack is MQTT? :question:

After being the first in my class, ahead of everyone else, I was able to look at the MQTT server. MQTT server is a service that allows us to connect via the M5Stack device and send data over the AWS Cloud.

## How to install and setup? :floppy_disk:
1. Make sure to have a new cleand EC2 instance. Type doesn't matter, I used the t2.micro
    1.1 Make sure to have an own security group which allows the necesarry port to connect to our instance. Open port: 1883.
2. Update and install the latest updates
3. Install the MQTT server


Following the changes made above, we must make some changes in the MQTT's config file directory. We need to specify that we want anonymous connections to get the messages to the M5Stack.

## MQQT config changes :wrench:
We need to create a new config file in /etc/mosquitto/conf.d , we will call it ***allowall.conf*** and it contains this one line:

```
allow_anonymous true
```

We will now be able to see the messages on the M5Stack. From a security perspective, this isn't very secure, but we just want to pretend we didn't know it.

## Run the MQTT service

To run the service there are different ways do to it but the result will be the same. 

We would run the command

```
sudo mosquitto -v -c /etc/mosquitto/mosquitto.conf
```
With this command, we will tell the MQTT service like listen dude, there is my configuration, and please run it with this one.


### MQTT output / log
This is the entire log from the MQTT after getting messages from the M5Stack.

```
1663201519: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663203320: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663205121: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663206922: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663208723: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663210524: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663212325: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663213098: New connection from 216.218.206.67:55042 on port 1883.
1663213098: New client connected from 216.218.206.67:55042 as MqttClient (p2, c1, k60).
1663213098: Client MqttClient closed its connection.
1663214126: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663215927: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663217728: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663219529: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663221330: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663223131: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663224932: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663226733: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663228534: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663230335: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663232136: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663233937: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663235738: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663236756: New connection from 178.32.197.84:39679 on port 1883.
1663236756: New client connected from 178.32.197.84:39679 as ONYPHE (p2, c1, k30).
1663236767: Client ONYPHE closed its connection.
1663237539: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663239340: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663241141: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663242942: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663244743: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663246544: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663247891: New connection from 167.248.133.60:60830 on port 1883.
1663247891: New client connected from 167.248.133.60:60830 as CENSYS (p2, c0, k10).
1663247906: Client CENSYS closed its connection.
1663248345: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663250146: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663251947: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663253748: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663255549: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663257350: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663259151: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663260952: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663262753: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663264554: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663266355: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663268156: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663269957: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663271758: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663273559: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663275360: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663277161: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663278962: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663280763: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663282564: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663283339: New connection from 23.90.160.146:36540 on port 1883.
1663283339: New client connected from 23.90.160.146:36540 as 3F409F67-FF6D-3123-18F3-AACB1EEB6257 (p2, c1, k10).
1663283339: Client 3F409F67-FF6D-3123-18F3-AACB1EEB6257 closed its connection.
1663284365: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663286166: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663287967: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663289768: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663289866: New connection from 167.248.133.61:58822 on port 1883.
1663289866: New client connected from 167.248.133.61:58822 as CENSYS (p2, c0, k10).
1663289882: Client CENSYS closed its connection.
1663291569: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663293370: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663295171: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663296972: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663298773: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663300574: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663302375: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663304176: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663305977: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663307778: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663309579: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663311380: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663313181: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663314982: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663316783: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663318584: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663320385: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663320855: New connection from 27.124.32.178:38950 on port 1883.
1663320855: Client <unknown> disconnected due to protocol error.
1663320855: New connection from 27.124.32.178:39090 on port 1883.
1663320865: Client <unknown> closed its connection.
1663320866: New connection from 27.124.32.178:41720 on port 1883.
1663320866: New client connected from 27.124.32.178:41720 as nmap (p2, c1, k30).
1663320885: Client nmap closed its connection.
1663320885: New connection from 27.124.32.178:48038 on port 1883.
1663320885: New client connected from 27.124.32.178:48038 as C1BD6FA3-D165-9933-87E0-DC07B4468BAF (p2, c1, k30).
1663320887: Client C1BD6FA3-D165-9933-87E0-DC07B4468BAF disconnected.
1663322186: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663323987: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663325788: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663327589: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663329390: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663331191: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663332992: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663334793: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663336594: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663337176: New connection from 64.62.197.167:11162 on port 1883.
1663337176: New client connected from 64.62.197.167:11162 as MqttClient (p2, c1, k60).
1663337176: Client MqttClient closed its connection.
1663338395: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663340196: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663341997: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663343798: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663344997: New connection from 36.106.167.101:1751 on port 1883.
1663344997: New client connected from 36.106.167.101:1751 as A𪛔 (p2, c1, k10, u'A𪛔').
1663345006: Client A𪛔 closed its connection.
1663345599: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663347400: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663349201: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663351002: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663352803: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663354604: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663356405: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663358206: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663360007: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663361808: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663363609: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663365410: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663367211: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663369012: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663370813: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663372614: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663374415: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663376216: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663378017: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663379818: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663380357: New connection from 216.218.206.68:44788 on port 1883.
1663380357: New client connected from 216.218.206.68:44788 as MqttClient (p2, c1, k60).
1663380357: Client MqttClient closed its connection.
1663381619: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663383420: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663385221: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663387022: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663388823: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663390624: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663392425: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663394226: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663396027: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663397828: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663399302: New connection from 167.94.138.117:34422 on port 1883.
1663399302: New client connected from 167.94.138.117:34422 as CENSYS (p2, c0, k10).
1663399318: Client CENSYS closed its connection.
1663399629: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663399720: New connection from 180.149.125.173:27025 on port 1883.
1663399720: Client <unknown> disconnected due to protocol error.
1663401430: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663403231: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663405032: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663406833: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663408634: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663410159: New connection from 167.94.146.59:48146 on port 1883.
1663410159: New client connected from 167.94.146.59:48146 as CENSYS (p2, c0, k10).
1663410174: Client CENSYS closed its connection.
1663410435: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663412236: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663414037: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663415838: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663417639: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663419440: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663421241: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663423042: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663424843: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663426644: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663428445: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663430246: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663432047: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663433848: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663435649: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663437450: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663439251: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663441052: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663442853: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663444654: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663446455: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663448256: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663450057: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663451858: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663453659: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663455460: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663457261: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663459062: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663460863: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663462664: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663464465: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663466266: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663467383: New connection from 64.62.197.92:60310 on port 1883.
1663467383: New client connected from 64.62.197.92:60310 as MqttClient (p2, c1, k60).
1663467383: Client MqttClient closed its connection.
1663468067: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663469868: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663471669: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663473470: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663475271: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663477072: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663478873: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663480674: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663482475: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663484276: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663486077: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663487878: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663489679: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663491480: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663493281: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663495082: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663496883: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663498684: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663500485: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663502286: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663504087: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663505888: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663507689: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663509490: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663511291: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663512481: New connection from 167.94.145.59:45392 on port 1883.
1663512481: New client connected from 167.94.145.59:45392 as CENSYS (p2, c0, k10).
1663512496: Client CENSYS closed its connection.
1663513092: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663514893: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663516694: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663518495: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663520296: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663522097: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663523898: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663525699: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663527500: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663529301: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663531102: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663532903: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663534704: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663536505: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663538306: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663540107: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663541908: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663543709: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663545510: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663547311: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663549112: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663550913: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663552714: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663554515: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663556316: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663558117: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663559918: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663561719: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663563520: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663565321: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663567122: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663568923: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663570724: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663572525: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663574326: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663576127: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663577928: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663579729: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663581530: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663583331: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663585132: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663586933: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663588734: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663590535: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663592336: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663594137: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663595938: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663596364: New connection from 64.62.197.212:28008 on port 1883.
1663596364: New client connected from 64.62.197.212:28008 as MqttClient (p2, c1, k60).
1663596364: Client MqttClient closed its connection.
1663597739: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663599540: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663601341: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663603142: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663604943: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663606744: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663607001: New connection from 167.248.133.63:59908 on port 1883.
1663607002: New client connected from 167.248.133.63:59908 as CENSYS (p2, c0, k10).
1663607017: Client CENSYS closed its connection.
1663608545: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663610346: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663612147: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663613948: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663615749: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663617550: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663619351: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663621152: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663622953: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663624754: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663626555: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663628356: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663630157: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663631958: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663632596: New connection from 159.223.61.151:61953 on port 1883.
1663632628: Client <unknown> closed its connection.
1663633759: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663635560: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663636627: New connection from 64.62.197.152:48714 on port 1883.
1663636627: New client connected from 64.62.197.152:48714 as MqttClient (p2, c1, k60).
1663636628: Client MqttClient closed its connection.
1663637361: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663639162: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663640519: New connection from 167.94.138.60:57866 on port 1883.
1663640519: New client connected from 167.94.138.60:57866 as CENSYS (p2, c0, k10).
1663640535: Client CENSYS closed its connection.
1663640963: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663642764: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663644565: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663646366: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663648167: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663649968: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663651769: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663653570: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663655371: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663657172: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663658973: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663660774: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663662575: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663664376: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663666177: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663667107: New connection from 161.189.161.138:36522 on port 1883.
1663667107: Client <unknown> disconnected due to protocol error.
1663667107: New connection from 161.189.161.138:45491 on port 1883.
1663667107: Client <unknown> disconnected due to protocol error.
1663667108: New connection from 161.189.161.138:24062 on port 1883.
1663667108: Client <unknown> disconnected due to protocol error.
1663667109: New connection from 104.218.164.32:16889 on port 1883.
1663667119: Client <unknown> disconnected: Success.
1663667119: New connection from 104.218.164.32:53578 on port 1883.
1663667119: Client <unknown> disconnected due to protocol error.
1663667120: New connection from 104.218.164.32:27038 on port 1883.
1663667120: Client <unknown> disconnected due to protocol error.
1663667978: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663669779: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663671580: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663673381: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663675182: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663676983: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663678784: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663680585: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663682386: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663684187: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663685988: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663686338: New connection from 167.248.133.117:40634 on port 1883.
1663686338: New client connected from 167.248.133.117:40634 as CENSYS (p2, c0, k10).
1663686353: Client CENSYS closed its connection.
1663687789: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663689590: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663691391: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663693192: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663694993: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663696794: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663698595: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663700396: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663702197: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663703998: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663705799: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663707600: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663709401: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663711202: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663713003: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663714804: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663716605: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663718406: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663720207: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663722008: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663723809: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663725610: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663727411: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663729212: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663731013: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663732245: New connection from 64.62.197.92:6830 on port 1883.
1663732245: New client connected from 64.62.197.92:6830 as MqttClient (p2, c1, k60).
1663732245: Client MqttClient closed its connection.
1663732814: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663734615: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663736416: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663738217: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663740018: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663741819: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663743620: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663745421: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663747222: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663749023: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663750824: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1663750996: mosquitto version 2.0.11 terminating
1663750996: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1664369370: mosquitto version 2.0.11 starting
1664369370: Config loaded from /etc/mosquitto/mosquitto.conf.
1664369370: Opening ipv4 listen socket on port 1883.
1664369370: mosquitto version 2.0.11 running
1664369608: mosquitto version 2.0.11 terminating
1664369608: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
1669063965: mosquitto version 2.0.11 starting
1669063965: Config loaded from /etc/mosquitto/mosquitto.conf.
1669063965: Opening ipv4 listen socket on port 1883.
1669063965: mosquitto version 2.0.11 running
1669065765: Saving in-memory database to /var/lib/mosquitto//mosquitto.db.
```