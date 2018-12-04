Immediate Tasks
===============
* Fix stepper driver heat sinks. **Need to do this before any big print jobs.** Either:
  * [heatsink adhesive][url_thermal_adhesive]; or
  * New [heatsinks with adhesive pads][url_heatsinks]; or
  * A bodge job with a drop of super glue
* Fine tune part-fan speed and Marlin to prevent `thermal runaway` error
  * Marlin config has been set to allow a 15°C variance (see config settings below), but should aim to reduce how much the thermistor is cooled
  * Could invest in a [heatblock insulator][url_heatblock_cover] to reduce the effect of the fans
  * Need to balance part cooling so it doesn't droop, and over-cooling the hotend
* Fine tune retraction settings
  * [Retraction Settings with Slic3r][url_retraction_reprap]
  * [Tip: printing with Bowden extruders][url_retraction_slic3r]
* Mount LCD. Personally I would look at either:
  * Printing a basic [mount][url_lcd_mount]; or
  * Making longer cables using ribbon cable and IDE connectors ([something like this][url_ribbon_Cable]) and then print a [case][url_lcd_case] to sit out the front

Future Improvements
===================
* Enable and configure [mesh bed leveling][url_marlin_auto_bed_level]
* Upgrade the linear bearings to remove play on X and Y axes. Would be worth hunting out and spending the money on decent quality ones so you don't just replace the existing ones with other loose fitting ones. Couple of NZ suppliers (unsure how good they are):
  * [Makershop LM8UU Linear Bearings][url_bearings_makershop]
  * [Mindkits LM8UU Linear Bearings][url_bearings_mindkits]
* Replace the PTFE tube in the hotend (currently a bit short making filament loading a little bit fiddly)
* Upgrade the extruder assembly for one with a spring tensioner (allows for small variances in filament width)
  * [Print one][url_bowden_stl] or
  * [Buy one][url_bowden_buy]
* Move extruder to opposite side to keep it away from the RAMPS board wiring
  * Would require a new stepper motor wire to reach the far side

Possible Changes ...for the LOLs
===============================
* Add an [Easy Peelzy removable flexible print surface][url_easy_peelzy]
  * I can highly recommend having a removable print bed
  * I can also highly recommend a flexible print bed
  * Haven't used this specific one, but everyone I follow raves about their value for money (only ~$20+pp)
* Reinstall the heatbed insulation: Honestly not sure how safe/unsafe having "cardboard" on the underside of an 80°c heatbed is?
* Replace hotend with a direct drive system (as opposed to bowden)
  * PROS: Better control of extrusion/retraction
  * CONS: Means the X carriage will be heavier (with the motor on it)
* Print a [cable chain][url_cable_chain_stl] for the heatbed wires (or [buy one][url_cable_chain_buy])
  * Less strain on the cables
  * Ensures cables don't get snagged
* Replace Z axis M8 threaded rods with [lead screws][url_lead_screw]
  * PROS: Sturdier Z axis (less wobble)
  * CONS: Need to print new X axis mounts

Current Configuration Settings
==============================
There are two configuration files in the Marlin firmware:
* `configuration.h`
* `Congiguration_adv.h`

The following tables contain settings that have been updated from the default settings.  The customisation is either a custom value for the setting, or uncommenting/commenting out the line to enable/disable to setting.

## configuration.h
|Setting|Description|Custom Value|
|-------|-----------|-----------:|
|USE_YMIN_PLUG|Defines that a Y Min endstop is installed|Disabled|
|USE_YMAX_PLUG|Defines that a Y Max endstop is installed|Enabled|
|X_MIN_ENDSTOP_INVERTING|Specifies that the endstop wiring is inverted i.e. ground = switch triggered|true|
|Z_MIN_ENDSTOP_INVERTING|Specifies that the endstop wiring is inverted i.e. ground = switch triggered|true|
|Y_MAX_ENDSTOP_INVERTING|Specifies that the endstop wiring is inverted i.e. ground = switch triggered|true|
|DEFAULT_AXIS_STEPS_PER_UNIT|The steps/mm for each of the stepper motors (X, Y, Z, Extruder)|(80, 80, 4000, 100)|
|X_PROBE_OFFSET_FROM_EXTRUDER|X offset: -left [of the nozzle] +right|*tba*|
|Y_PROBE_OFFSET_FROM_EXTRUDER|Y offset: -front [of the nozzle] +behind|*tba*|
|Z_PROBE_OFFSET_FROM_EXTRUDER|Z offset: -below [the nozzle]|*tba*|
|Y_HOME_DIR|Homing direction for Y axis: -1 = min; 1 = max|1|
|X_BED_SIZE|Print bed size in the X axis|190|
|Y_BED_SIZE|Print bed size in the Y axis|190|
|Z_MAX_POS|Maximum Z height|180|

## Configuration_adv.h
|Setting|Description|Custom Value|
|-------|-----------|-----------:|

Useful Links
============
[Marlin firmware homepage][url_marlin]  
[Marlin configuration guide][url_marlin_config]  
[RAMPS 1.4 controller board homepage][url_ramps]  
[RAMPS 1.4 wiring guide][url_ramps_wiring] 
[Slic3r Manual][url_slic3r_manual]

<!----------------------------------------------------->
<!--    URL Tags                                     -->
<!----------------------------------------------------->
[url_marlin]:http://marlinfw.org/
[url_marlin_config]:http://marlinfw.org/docs/configuration/configuration.html
[url_marlin-config_h]:http://marlinfw.org/docs/configuration/configuration.html#configuration.h
[url_marlin_config_adv]:http://marlinfw.org/docs/configuration/configuration.html#configuration_adv.h
[url_marlin_auto_bed_level]:http://marlinfw.org/docs/configuration/configuration.html#bed-leveling
[url_ramps]:https://reprap.org/wiki/RAMPS_1.4
[url_ramps_wiring]:https://reprap.org/wiki/RAMPS_1.4#Wiring
[url_slic3r_manual]:https://manual.slic3r.org/
[url_retraction_reprap]:https://reprap.org/wiki/Retraction_Tuning_With_Slic3r
[url_retraction_slic3r]:https://slic3r.org/blog/tip-bowden-extruders/
[url_bearings_makershop]:http://www.makershop.co.nz/Bearings/8mmLinear/LM8UU
[url_bearings_mindkits]:http://www.mindkits.co.nz/lm8uu-linear-bearings-for-3d-printer.aspx
[url_cable_chain_stl]:https://www.thingiverse.com/search?sort=relevant&q=cable+chain+heatbed&type=things&dwh=765c05b804a8dff
[url_cable_chain_buy]:https://www.banggood.com/15mm-x-20mm-R28-Plastic-Cable-Semi-closed-Drag-Chain-Wire-Carrier-Length-1000mm-p-1069454.html?rmmds=detail-top-buytogether-auto&bundleRecToken=ChM2NjU0NDI2ODU3MTUwMzYxMjcyEAIaAkJUIgZGQlRfUEQoAA&cur_warehouse=CN
[url_heatblock_cover]:https://www.banggood.com/3Pcs-Green-Silicone-Case-For-E3D-V6-Heater-Block-3D-Printer-Parts-p-1276877.html?rmmds=search&cur_warehouse=CN
[url_bowden_stl]:https://www.thingiverse.com/thing:669459
[url_bowden_buy]:https://www.banggood.com/Full-Metal-Remote-Extrusion-Feeding-Machine-Bowden-Extruder-For-1_75mm-Filament-Anet-A8-Prusa-I3-p-1350130.html?rmmds=search&cur_warehouse=CN
[url_heatsinks]:https://www.banggood.com/Aluminum-995mm-Heat-Sink-With-Adhesive-For-A4988-Stepper-Motor-Driver-Module-3D-Printer-p-1212893.html?rmmds=search&cur_warehouse=CN
[url_thermal_adhesive]:https://www.banggood.com/STARS-922-Heatsink-Plaster-CPU-Thermal-Conductive-Glue-With-Strong-Adhesive-For-3D-Printer-p-1297296.html?rmmds=search&cur_warehouse=CN
[url_easy_peelzy]:https://www.3d-easy.xyz/store/p2/Easy-Peelzy.html
[url_lead_screw]:https://www.banggood.com/8mm-300400500600mm-Lead-2mm-Stainless-Steel-Leadscrew-T8-Nut-For-CNC-3D-Printer-Reprap-p-1143904.html?rmmds=search&ID=49053&cur_warehouse=CN
[url_ribbon_cable]:https://www.aliexpress.com/item/10P-60cm-12864-LCD-2004-LCD-Extension-Cable-MKS-Prusa-Ramps-RepRap-Anet-i3-FT5-3D/32883311114.html?spm=2114.search0104.3.1.303113e84JJeeL&ws_ab_test=searchweb0_0,searchweb201602_4_10065_10068_10547_319_10059_10884_317_10548_10887_10696_100031_321_322_10084_453_10083_454_10103_10618_10307_537_536,searchweb201603_51,ppcSwitch_0&algo_expid=53c01887-06a5-452f-a8d1-609eb09f5059-0&algo_pvid=53c01887-06a5-452f-a8d1-609eb09f5059
[url_lcd_case]:https://www.thingiverse.com/thing:2161283
[url_lcd_mount]:https://www.thingiverse.com/thing:120266