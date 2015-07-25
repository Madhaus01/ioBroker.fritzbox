![Logo](admin/fritzbox.png)
ioBroker fritzbox Adapter
===========================


## Changelog
### 0.2.1 (2015-06-28)
* (ruhr) more configuration options

### 0.2.0 (2015-06-26)
* (ruhr) 

## Install

```node iobroker.js add fritzbox```

## Configuration

## Dokumentation der Objekte

Unter **fritzbox.x.** legt der Adapter folgende Channel und Objekte an:

* message                                 (Meldung aus der Fritzbox)

* **calls.                                  (CHANNEL)**
* calls.ring                              (true/false, steht ein Ruf an?)
* calls.missedCount                       (Integer, read & write, Anzahl verpasster Anrufe)
* calls.missedDateReset                   (Datum, zu dem calls.missedCount auf 0 gesetzt wurde
* calls.ringActualNumber                  (aktuell anstehender Ruf (der Letzte, wenn es mehrere gibt))
* calls.ringActualNumbers                 (alle aktuell anstehenden Rufe)
* calls.ringLastNumber                    (letzter Anrufer)
* calls.ringLastMissedNumber              (letzter verpasster Anrufer)
* calls.callLastNumber                    (Wahlwiederholung, letzte gewählte Rufnummer)
* calls.connectNumber                     (letztes aktuell verbundenes Gespräch)
* calls.connectNumbers                    (alle aktuell verbundenen Gespräche)

* **calls.counterActualCalls.               (CHANNEL - Realtime)**
* calls.counterActualCalls.ringCount      (Anzahl der anstehenden Anrufe (RING))
* calls.counterActualCalls.callCount      (Anzahl der gehenden Anrufversuche (CALL))
* calls.counterActualCalls.connectCount   (Anzahl der bestehenden Gespräche (CONNECT))
* calls.counterActualCalls.allActiveCount (Anzahl aktiver Anrufe (CALL, RING & CONNECT)

* **calls.telLinks.                         (CHANNEL - wählbare Rufnummern tel:+...)**
* calls.telLinks.ringLastNumberTel        (letzter Anrufer als wählbarer Link)
* calls.telLinks.ringLastMissedNumberTel  (letzter verpasster Anrufer als wählbarer Link)
* calls.telLinks.callLastNumberTel        (Wahlwiederholung, letzte gewählte Rufnummer, wählbar)

* **history.                                (CHANNEL)**
* history.allTableTxt                     (...)
* history.allTableHTML                    (Anruferliste als html Tabelle)
* history.allTableJSON                    (Anruferliste als JSON)
* history.missedTableHTML                 (Liste verpasste Anrufe als html)
* history.missedTableJSON                 (Liste verpasste Anrufe als JSON)

* **history.cdr.                            (CHANNEL)**
* history.cdr.json                        (CDR als JSON)
* history.cdr.html                        (CDR als html)
* history.cdr.txt                         (CDR als txt)
* history.cdr.missedJSON                  (letzter verpasster Anruf als JSON)
* history.cdr.missedHTML                  (letzte verpasster Anruf als html)

* **callmonitor.                            (CHANNEL - Realtime)**
* callmonitor.all                         (html Liste: alle aktiven Anrufe in allen Zuständen)
* callmonitor.ring                        (html Liste: alle aktiven Anrufe
* callmonitor.call                        (html Liste: alle gehenden Gespräche)
* callmonitor.connect                     (html Liste: alle verbundenen Gespräche)

* **system.                                 (CHANNEL)**
* system.deltaTime                        (Deltazeit zwischen System und Fritzbox in Sek.)
* system.deltaTimeOK                      (true/false Deltazeit zwischen System und Fritzbox in der Tolereanz)


## Beispiel-Widgets

### Fritzbox Widget in groß

Enthält:

* 

![Fritzbox Widget groß](doc/iobroker_fritzbox_widget_gross.png)

[ioBroker Fritzbox Widget in groß als VIS Importdatei](widgets/iobroker_fritzbox_widget_gross.png)

```
[{"tpl":"tplValueString","data":{"oid":"","visibility-cond":"==","visibility-val":1,"visibility-oid":"","html_prepend":"","html_append":"","comment":""},"style":{"left":"10px","top":"10px","width":"564px","height":"655px","color":"rgb(68, 68, 68)","text-align":"center","font-size":"18px","background":"whitesmoke","padding-right":"","padding-top":"0px","z-index":"","border-radius":"20px"},"widgetSet":"basic"},{"tpl":"tplValueStringRaw","data":{"oid":"fritzbox.0.history.allTableHTML","visibility-cond":"==","visibility-val":1,"comment":""},"style":{"left":"20px","top":"445px","background":"lightgrey","width":"536px","height":"199px","padding":"","padding-left":"8px","padding-top":"8px","font-family":"\"Courier New\", Courier, monospace","font-weight":"","font-size":"small"},"widgetSet":"basic"},{"tpl":"tplValueStringRaw","data":{"oid":"fritzbox.0.history.missedTableHTML","visibility-cond":"==","visibility-val":1,"comment":""},"style":{"left":"195px","top":"305px","background":"lightgrey","width":"360px","height":"91px","padding":"","padding-left":"8px","padding-top":"8px","font-family":"\"Courier New\",Courier,monospace","color":"rgb(34, 34, 34)","text-align":"start","text-shadow":"none","font-style":"normal","font-variant":"normal","font-weight":"400","font-size":"13px"},"widgetSet":"basic"},{"tpl":"tplValueString","data":{"oid":"fritzbox.0.calls.counterActualCalls.ringCount","visibility-cond":"==","visibility-val":"9","visibility-oid":"","html_prepend":"<span style=\"font-size: 20px; padding: 0 20px 0 0;\">Rufe: </span>","html_append":"","name":"fritzbox - Anzeige aktuelle Rufe (RING)","comment":""},"style":{"left":"20px","top":"75px","width":"154px","height":"40px","color":"ghostwhite","text-align":"right","font-size":"28px","background":"darkslategray","padding-right":"10px","padding-top":"4px","z-index":"5","padding-left":"","line-height":"40px"},"widgetSet":"basic"},{"tpl":"tplHtml","data":{"visibility-cond":"==","visibility-val":1,"refreshInterval":"0","html":"<span style=\"color:red; \" >Anrufe</span> - <span style=\"color:blue; \" >Rufaufbau</span> - <span style=\"color:green; \" >Gespräche</span>","comment":""},"style":{"left":"195px","top":"195px","width":"369px","height":"24px","color":"rgb(68, 68, 68)","text-align":"center","font-family":"Arial, sans-serif","font-style":"normal","font-variant":"normal","font-weight":"400","font-size":"18px","background":"rgb(204, 204, 204) none repeat scroll 0% 0% / auto padding-box border-box","padding":"","z-index":"15","line-height":"24px"},"widgetSet":"basic"},{"tpl":"tplValueString","data":{"oid":"fritzbox.0.calls.counterActualCalls.connectCount","visibility-cond":"==","visibility-val":"9","visibility-oid":"","html_prepend":"<span style=\"font-size: 20px; padding: 0 20px 0 0;\">Gespräche: </span>","html_append":"","name":"fritzbox - Anzahl aktiver Gespräche (CONNECT)","comment":""},"style":{"left":"20px","top":"175px","width":"154px","height":"40px","color":"ghostwhite","text-align":"right","font-size":"28px","background":"darkslategray","padding-right":"10px","padding-top":"4px","z-index":"5","padding-left":"","line-height":"40px"},"widgetSet":"basic"},{"tpl":"tplValueString","data":{"oid":"fritzbox.0.calls.counterActualCalls.callCount","visibility-cond":"==","visibility-val":"9","visibility-oid":"","html_prepend":"<span style=\"font-size: 20px; padding: 0 20px 0 0;\">Rufaufbau: </span>","html_append":"","name":"fritzbox - Anzeige aktiver geh. Gesprächsaufbauten (CALL)","comment":""},"style":{"left":"20px","top":"125px","width":"154px","height":"40px","color":"ghostwhite","text-align":"right","font-size":"28px","background":"darkslategray","padding-right":"10px","padding-top":"4px","z-index":"5","padding-left":"","line-height":"40px"},"widgetSet":"basic"},{"tpl":"tplHtml","data":{"visibility-cond":"==","visibility-val":1,"refreshInterval":"0","html":"Anruferliste html","comment":""},"style":{"left":"20px","top":"420px","width":"544px","height":"24px","color":"rgb(245, 245, 245)","text-align":"center","font-family":"Arial, sans-serif","font-style":"normal","font-variant":"normal","font-weight":"400","font-size":"18px","background":"rgb(105, 105, 105) none repeat scroll 0% 0% / auto padding-box border-box","padding":"","z-index":"auto","padding-top":"","line-height":"24px"},"widgetSet":"basic"},{"tpl":"tplHtml","data":{"visibility-cond":"==","visibility-val":1,"refreshInterval":"0","html":"Verpasste Anrufe","comment":""},"style":{"left":"195px","top":"280px","width":"368px","height":"24px","color":"rgb(245, 245, 245)","text-align":"center","font-family":"Arial, sans-serif","font-style":"normal","font-variant":"normal","font-weight":"400","font-size":"18px","background":"rgb(105, 105, 105) none repeat scroll 0% 0% / auto padding-box border-box","padding":"","z-index":"auto","line-height":"24px"},"widgetSet":"basic"},{"tpl":"tplValueListHtml8","data":{"oid":"fritzbox.0.calls.ring","visibility-cond":"==","visibility-val":1,"count":"1","value1":"Anruf von  {fritzbox.0.calls.ringActualNumber}","style0":"background-color:lightgrey; color:black;  font-size: 30px; padding: 0 20px 0 0;","style1":"background-color:red; color:white; font-size: 30px;","value0":"","test_list":"1","name":"fritzbox - Anzeige aktueller Anrufer (rot)","comment":""},"style":{"left":"20px","top":"20px","text-align":"center","width":"544px","height":"44px","font-family":"Arial, sans-serif","font-style":"normal","font-variant":"normal","font-weight":"400","font-size":"16px","z-index":"15","color":"rgb(245, 245, 245)","background":"rgb(47, 79, 79) none repeat scroll 0% 0% / auto padding-box border-box","padding":"","padding-top":"","line-height":"44px"},"widgetSet":"basic"},{"tpl":"tplRLiveChart","data":{"visibility-cond":"==","visibility-val":1,"line_color1":"red","line_color2":"green","line_color3":"blue","line_color4":"black","line_color5":"black","line_color6":"black","line_color7":"black","line_color8":"black","line_thick1":"2","line_thick2":"2","line_thick3":"2","line_thick4":"1","line_thick5":"1","line_thick6":"1","line_thick7":"1","line_thick8":"1","min_value":"0","max_value":"0","factor":"1","value_offset":"0","update_interval":"5000","points_count":"250","num_hlines":"3","oid1":"fritzbox.0.calls.counterActualCalls.ringCount","oid2":"fritzbox.0.calls.counterActualCalls.connectCount","oid3":"fritzbox.0.calls.counterActualCalls.callCount","comment":""},"style":{"left":"170px","top":"85px","width":408,"height":131,"z-index":"4"},"widgetSet":"RGraph"},{"tpl":"tplHtml","data":{"visibility-cond":"==","visibility-val":1,"refreshInterval":"0","html":"Anrufe","comment":""},"style":{"left":"195px","top":"75px","width":"369px","height":"24px","color":"rgb(245, 245, 245)","text-align":"center","font-family":"Arial, sans-serif","font-style":"normal","font-variant":"normal","font-weight":"400","font-size":"18px","background":"rgb(105, 105, 105) none repeat scroll 0% 0% / auto padding-box border-box","padding":"","z-index":"auto","padding-top":"3px","line-height":"24px"},"widgetSet":"basic"},{"tpl":"tplValueString","data":{"oid":"fritzbox.0.calls.missedCount","visibility-cond":"==","visibility-val":"9","visibility-oid":"","html_prepend":"<span style=\"font-size: 20px; padding: 0 20px 0 0;\">Verpasst:</span>","html_append":"","name":"fritzbox - Anzeige Anzahl verpasster Anrufe","comment":""},"style":{"left":"195px","top":"225px","width":"154px","height":"40px","color":"ghostwhite","text-align":"right","font-size":"28px","background":"darkslategray","padding-right":"10px","padding-top":"4px","z-index":"5","padding-left":"","line-height":"40px"},"widgetSet":"basic"},{"tpl":"tplValueString","data":{"oid":"fritzbox.0.system.deltaTime","visibility-cond":"==","visibility-val":"false","visibility-oid":"fritzbox.0.system.deltaTimeOK","html_prepend":"<span style=\"font-size: 14px; padding: 0 20px 0 0;\">Delta Zeit Fritzbox / System: </span>","html_append":"<span style=\"font-size: 14px; padding: 0 20px 0 0;\"> Sek</span>","name":"fritzbox - Delta Zeit Fritzbox vs. Systemzeit","comment":""},"style":{"left":"20px","top":"20px","width":"533px","height":"40px","color":"black","text-align":"right","font-size":"30px","background":"yellow","padding-right":"10px","padding-top":"4px","z-index":"3","padding-left":"","line-height":"40px"},"widgetSet":"basic"},{"tpl":"tplValueString","data":{"oid":"fritzbox.0.calls.counterActualCalls.allActiveCount","visibility-cond":"==","visibility-val":"9","visibility-oid":"","html_prepend":"<span style=\"font-size: 20px; padding: 0 20px 0 0;\">Alle: </span>","html_append":"","name":"fritzbox - Anzahl aktiver Gespräche (CONNECT)","comment":""},"style":{"left":"20px","top":"225px","width":"154px","height":"40px","color":"ghostwhite","text-align":"right","font-size":"28px","background":"darkslategray","padding-right":"10px","padding-top":"4px","z-index":"5","padding-left":"","line-height":"40px"},"widgetSet":"basic"},{"tpl":"tplValueString","data":{"oid":"fritzbox.0.system.deltaTime","visibility-cond":"==","visibility-val":"false","visibility-oid":"fritzbox.0.system.deltaTimeOK","html_prepend":"<span style=\"font-size: 14px; padding: 0 20px 0 0;\">Delta Zeit Fritzbox /<br> System: <br><br></span>","html_append":"<span style=\"font-size: 14px; padding: 0 20px 0 0;\"> Sek</span>","name":"fritzbox - Delta Zeit Fritzbox vs. Systemzeit","comment":""},"style":{"left":"20px","top":"280px","width":"146px","height":"120px","color":"black","text-align":"left","font-size":"30px","background":"yellow","padding-right":"10px","padding-top":"4px","z-index":"20","padding-left":"8px","line-height":"20px","margin-left":""},"widgetSet":"basic"},{"tpl":"tplBasicState","data":{"oid":"fritzbox.0.calls.missedCount","visibility-cond":"==","visibility-val":"","value":"0","html":"verpasste Anrufe Löschen","visibility-oid":"","name":"","comment":""},"style":{"left":"365px","top":"225px","background":"rgb(204, 204, 204) none repeat scroll 0% 0% / auto padding-box border-box","width":"90px","height":"42px","z-index":"10","color":"rgb(68, 68, 68)","text-align":"center","text-shadow":"none","font-family":"'Lucida Grande', 'Lucida Sans', Arial, sans-serif","font-style":"normal","font-variant":"normal","font-weight":"bold","font-size":"12px","line-height":"14px","letter-spacing":"0","word-spacing":"0px","background-position":"0% 0%","background-size":"auto","background-clip":"","background-origin":"","padding":"","box-shadow":"0px 0px 1px 1px","border-style":"solid","border-radius":"","border-width":"1px"},"widgetSet":"basic"},{"tpl":"tplValueString","data":{"oid":"fritzbox.0.calls.missedDateReset","visibility-cond":"==","visibility-val":1,"html_prepend":"seit dem<br>"},"style":{"left":"465px","top":"220px","z-index":"30","height":"60px","width":"98px"},"widgetSet":"basic"}]
```



## todo
* Doku der Datenpunkte
* Import des xml Telefonbuch der Fritzbox
* Feinere Konfiguration der Anruferliste (Tabellen)

## License

The MIT License (MIT)

Copyright (c) 2015, ruhr70

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
