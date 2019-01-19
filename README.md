# Raspberry Pi IoT Water Quality Controller
A Raspberry Pi based controller that can be used for water treatment systems, hydroponics, aeroponics, aquaponics, reef tanks and similar applications.

The inspiration came from [reef-pi](https://github.com/reef-pi/reef-pi). There's a great write up on that project over at [Adafruit](https://learn.adafruit.com/search?q=reef-pi). This is simply a variation on the same theme that's better suited to what I'm doing. Rather than a web interface, this is  Python based so it can exchange information via MQTT and other protocols.

**Full Disclosure: This is one of my infamous cocktail napkin designs and should be considered a work in progress for now.**

## Hardware
### Water Quality Sensing
Atlas Scientific offers a stackable HAT for Raspberry Pi called Tentacle T3 for their EZO boards and sensors. It provides two isolated, one non-isolated and two spare channels. 

I'm using the non-isolated for RTD temperature and the other two for PH and electrical conductivity (total dissolved solids). Normally the spare channels would be used for dosing pumps but I've repurposed one for dissolved oxygen by adding an additional isolated carrier board. Something similar can be done with channel 5.

* [Whitebox Labs Tentacle T3](https://www.atlas-scientific.com/product_pages/components/tentacle-t3.html)
* [Electrically Isolated EZO™ Carrier Board](https://www.atlas-scientific.com/product_pages/components/single_carrier_iso.html)
  * [EZO RTD](https://www.atlas-scientific.com/product_pages/circuits/ezo_rtd.html)
  * [EZO PH](https://www.atlas-scientific.com/product_pages/circuits/ezo_ph.html)
  * [EZO EC](https://www.atlas-scientific.com/product_pages/circuits/ezo_ec.html)
  * [EZO DO](https://www.atlas-scientific.com/product_pages/circuits/ezo_do.html)

![Sensor](/images/hydro_sensor_bb.png)

### Dosing
Adafruit offers a 12V DC motor controller HAT with four channels. I'm using those for PH up, PH down and two nutrient solutions.

* [Adafruit DC & Stepper Motor HAT for Raspberry Pi](https://www.adafruit.com/product/2348)
* [Peristaltic Liquid Pump](https://www.adafruit.com/product/1150 )

![Dosing](/images/hydro_12V_PWM_bb.png)

### Chillers and Pumps
The Adafruit HAT is great for 12VDC PWM but isn't designed to switch lager loads. For that I'm using a MOSFET board.

* [Diymore 4 Channels 4 Route MOSFET](https://www.amazon.com/Diymore-Channels-MOSFET-Button-Arduino/dp/B01MRQFYJN/ref=asc_df_B01MRQFYJN/?tag=hyprod-20&linkCode=df0&hvadid=198109700569&hvpos=1o3&hvnetw=g&hvrand=1418185042287151470&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9007347&hvtargid=pla-385355383830&psc=1)
 * [IceProbe Thermoelectric Aquarium Chiller](https://smile.amazon.com/IceProbe-Thermoelectric-Aquarium-Chiller/dp/B001JSVLBO/ref=cm_cr_arp_d_product_top?ie=UTF8)
 * [12v Submersible Water Pump 206 GPH](https://www.amazon.com/dp/B01816E1YU/ref=psdc_402303011_t2_B01267CT80?th=1)

![Chillers and Pumps](/images/hydro_12V_DC_bb.png)

