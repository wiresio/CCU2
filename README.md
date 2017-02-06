Upload device description:
- ssh CCU2
- cd /var
- more ids
- BidCoS-Address=HMIDOFYOURHOMEMATICINTERFACE -> HMID of CCU2
- cd /firmware/rftypes/ -> XML
- mount -o remount,rw /
- chmod 755 rf_s_1conf_644_le_v1_5.xml

Add to /www/webui/webui.js:
- DEV_LIST.push('HM-LC-Sw1PBU-FM-CUSTOM');
- DEV_DESCRIPTION["HM-LC-Sw1PBU-FM-CUSTOM"] = "HM-LC-Sw1PBU-FM-CUSTOM";
- DEV_PATHS["HM-LC-Sw1PBU-FM-CUSTOM"] = new Object();
- DEV_PATHS["HM-LC-Sw1PBU-FM-CUSTOM"]["50"] = "/config/img/devices/50/PushButton-2ch-wm_thumb.png";
- DEV_PATHS["HM-LC-Sw1PBU-FM-CUSTOM"]["250"] = "/config/img/devices/250/PushButton-2ch-wm.png";
- DEV_HIGHLIGHT["HM-LC-Sw1PBU-FM-CUSTOM"] = new Object();
- DEV_HIGHLIGHT["HM-LC-Sw1PBU-FM-CUSTOM"]["1"] = [2, 0.244, 0.312, 0.428, 0.168];
- DEV_HIGHLIGHT["HM-LC-Sw1PBU-FM-CUSTOM"]["2"] = [2, 0.244, 0.56, 0.428, 0.168];

Adapt /www/config/devdescr/DEVB.tcl, in line 4 add entry:
- HM-LC-Sw1PBU-FM-CUSTOM {{50 /config/img/devices/50/PushButton-2ch-wm_thumb.png} {250 /config/img/devices/250/PushButton-2ch-wm.png}}

Finish:
- mount -o remount,ro /
