---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Component
Hooks
(useState, UseEffect)
(JSX returned ) ^aYdF9l85

Life Cycle ^zztTj2Ty

React ^cElr8BCT

Initial render (mount) ^0wCPX5C4

Re-Rendering (Updating) ^zuvXJJ2r

Exit (Unmounting) ^o5ouD0yF

Lo que el usuario finalmente ve ^9oUw4zfd

Ejecutara todo el código dentro de la función ^sBdigUms

Inicializara todos los valores ya sean Hooks o constantes y variables ^yLCKbZqj

JSX ^SwmSqmvD

Virtual dom ^SUM0Z9n9

Va hacer un return hacia primero el virtual DOM ^1vbSAKhB

Lo pasara al virtual DOM para hacer las actualizaciones que sean necesarias comparadas con el DOM ^M9wLNIBm

DOM ^BTXrImWq

Programa todos los hooks una vez hecha esta secuencia ^wK9S6uE6

Ejecuta todo ^icxqX7Dh

Ejecuta todo lo que se haya dejado dentro de useEffect ^dfnvHAAB

Lo que ocurra después en el useEffet se renderizara de manera sincrona ^orw28LGb

Ya que useEffect se ejecutara después del renderizado del componente ^RN0e1dzZ

useLayoutEffect ^N9EbiLSF

Si necesitamos que se ejecute algo antes de que se muestre en el navegador necesitaríamos usar ^PnjwDwUM

  ^90lmH2PW

Ejecutara todo el código dentro de la función denuevo ^ekaHAf46

Volverá a calcular todos los valores ya sean Hooks o constantes y variables ^a1npfOsd

Virtual dom ^ZMjEXRch

Va hacer un return hacia primero el virtual DOM ^XfMSAn0K

Lo pasara al virtual DOM para hacer las actualizaciones que sean necesarias comparadas con el DOM ^dCTOHF2A

DOM ^5vcXEpsE

Ejecuta todo ^0kE5YOzv

JSX ^BvlXUKKM

Acá también va a volver a re-ejecutar useEffect por si el caso que poseemos alguna dependencia que fue actualizada ^Brw2Wg5w

Esto sucede cuando ya no es necesario tener un componente en pantalla, por ejemplo navegaciones de pantalla o cambia un valor del componente cual hace que no se renderize ^Uz7xpOWU

Lo primero que hará es liberar todos los valores de la memoria  
(useState, useMemo, const, vars...) ^jEOjZSeB

Ejecutaran cleanups functions como las del useEffect ^ocRbLPNj

Si tenemos funciones de limpieza un ejemplo es el return de useEffect ^pRokJwHo

Ejecutaran cleanups functions como las del useEffect ^pTgVSlwP

Virtual dom ^1iQz0Ec5

Va hacer un return hacia primero el virtual DOM ^lVcUrzr7

Lo pasara al virtual DOM para hacer las actualizaciones que sean necesarias comparadas con el DOM ^mFB4y8wT

DOM ^rBCecqjY

JSX ^hxKoD4fQ

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.23",
	"elements": [
		{
			"type": "ellipse",
			"version": 470,
			"versionNonce": 1698691113,
			"isDeleted": false,
			"id": "NB3PpWU_jiUOqkitT3loJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1116.0301201664315,
			"y": -390.65651226341663,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 370.94040112781323,
			"height": 202.99314674428825,
			"seed": 2088323177,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "aYdF9l85"
				},
				{
					"id": "nN0HvzBl6MUlAJvl16Gv0",
					"type": "arrow"
				}
			],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 545,
			"versionNonce": 150584039,
			"isDeleted": false,
			"id": "aYdF9l85",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1042.547022767476,
			"y": -338.9288541899136,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 223.6797332763672,
			"height": 100,
			"seed": 754611785,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Component\nHooks\n(useState, UseEffect)\n(JSX returned )",
			"rawText": "Component\nHooks\n(useState, UseEffect)\n(JSX returned )",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "NB3PpWU_jiUOqkitT3loJ",
			"originalText": "Component\nHooks\n(useState, UseEffect)\n(JSX returned )",
			"lineHeight": 1.25,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 412,
			"versionNonce": 1646558311,
			"isDeleted": false,
			"id": "nN0HvzBl6MUlAJvl16Gv0",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -731.0303006745764,
			"y": -281.50375068144575,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 310.0886376493273,
			"height": 3.2924078793977856,
			"seed": 1155599655,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "cElr8BCT"
				}
			],
			"updated": 1745111135265,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NB3PpWU_jiUOqkitT3loJ",
				"gap": 14.49550010317239,
				"focus": 0.05454975871617696
			},
			"endBinding": {
				"elementId": "exjRsR1I5-QDSzCB-513H",
				"gap": 13.720465831277522,
				"focus": -0.008427002569987282
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					310.0886376493273,
					3.2924078793977856
				]
			]
		},
		{
			"type": "text",
			"version": 49,
			"versionNonce": 1206896135,
			"isDeleted": false,
			"id": "cElr8BCT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -606.8158700472424,
			"y": -291.6665518899453,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 59.179931640625,
			"height": 25,
			"seed": 463280585,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "React",
			"rawText": "React",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "nN0HvzBl6MUlAJvl16Gv0",
			"originalText": "React",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "diamond",
			"version": 169,
			"versionNonce": 1146929641,
			"isDeleted": false,
			"id": "exjRsR1I5-QDSzCB-513H",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -407.2267723559487,
			"y": -381.00029208649414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 210.02331531198547,
			"height": 206.3600917838723,
			"seed": 2025792551,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "nN0HvzBl6MUlAJvl16Gv0",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "zztTj2Ty"
				},
				{
					"id": "XBBYqapkfrxrvFX3j4Zwe",
					"type": "arrow"
				},
				{
					"id": "u61zjkQZVpnWobbGj0nHY",
					"type": "arrow"
				},
				{
					"id": "d5GmR41pJn5QlDXKe1DOH",
					"type": "arrow"
				}
			],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 80,
			"versionNonce": 1312255271,
			"isDeleted": false,
			"id": "zztTj2Ty",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -326.47092063976874,
			"y": -302.91026914052605,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 48.49995422363281,
			"height": 50,
			"seed": 1544255849,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Life\nCycle",
			"rawText": "Life Cycle",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "exjRsR1I5-QDSzCB-513H",
			"originalText": "Life Cycle",
			"lineHeight": 1.25,
			"baseline": 42
		},
		{
			"type": "rectangle",
			"version": 478,
			"versionNonce": 1696505033,
			"isDeleted": false,
			"id": "jq_XytFKDj197ea-ABRlY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -942.3013224404908,
			"y": -36.79364437498401,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 278.4029843114771,
			"height": 75.70608522763916,
			"seed": 97988231,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "0wCPX5C4"
				},
				{
					"id": "XBBYqapkfrxrvFX3j4Zwe",
					"type": "arrow"
				},
				{
					"id": "qghMXz80WXXGH6Lq3NMVl",
					"type": "arrow"
				},
				{
					"id": "SDyjQ2Ct-kJpP9IkFdTYs",
					"type": "arrow"
				}
			],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 421,
			"versionNonce": 2000498759,
			"isDeleted": false,
			"id": "0wCPX5C4",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -907.8497158438342,
			"y": -11.44060176116443,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 209.49977111816406,
			"height": 25,
			"seed": 1904946697,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Initial render (mount)",
			"rawText": "Initial render (mount)",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "jq_XytFKDj197ea-ABRlY",
			"originalText": "Initial render (mount)",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "arrow",
			"version": 656,
			"versionNonce": 405199879,
			"isDeleted": false,
			"id": "XBBYqapkfrxrvFX3j4Zwe",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -380.36315370183786,
			"y": -229.5881987014129,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 392.6038826475826,
			"height": 181.80499164036522,
			"seed": 630556519,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111135265,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "exjRsR1I5-QDSzCB-513H",
				"gap": 15.57632269686242,
				"focus": -0.3431951922124227
			},
			"endBinding": {
				"elementId": "jq_XytFKDj197ea-ABRlY",
				"gap": 10.989562686063664,
				"focus": -0.22280248572295452
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-156.29644794070998,
					25.64236431427986
				],
				[
					-392.6038826475826,
					181.80499164036522
				]
			]
		},
		{
			"type": "rectangle",
			"version": 183,
			"versionNonce": 2094894951,
			"isDeleted": false,
			"id": "SPnRvN5O-24umwObDE-vB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -447.5075205999267,
			"y": -44.7807849171063,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 342.1840213397249,
			"height": 70.4496678934409,
			"seed": 1576858439,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "zuvXJJ2r"
				},
				{
					"id": "u61zjkQZVpnWobbGj0nHY",
					"type": "arrow"
				},
				{
					"id": "qghMXz80WXXGH6Lq3NMVl",
					"type": "arrow"
				},
				{
					"id": "ov8cvwNWA4mNGrqEYOoRO",
					"type": "arrow"
				},
				{
					"id": "g3PfQ9YGBQVKho_5FDTL9",
					"type": "arrow"
				}
			],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 1964162697,
			"isDeleted": false,
			"id": "zuvXJJ2r",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -391.5053765682478,
			"y": -22.05595097038585,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 230.1797332763672,
			"height": 25,
			"seed": 636471143,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Re-Rendering (Updating)",
			"rawText": "Re-Rendering (Updating)",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "SPnRvN5O-24umwObDE-vB",
			"originalText": "Re-Rendering (Updating)",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "rectangle",
			"version": 322,
			"versionNonce": 2021269671,
			"isDeleted": false,
			"id": "AlkB-gdZlAU6e-3WVIYoQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 156.5937934150044,
			"y": -31.415850014766164,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 342.1840213397249,
			"height": 70.4496678934409,
			"seed": 795506729,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "o5ouD0yF"
				},
				{
					"id": "d5GmR41pJn5QlDXKe1DOH",
					"type": "arrow"
				},
				{
					"id": "ov8cvwNWA4mNGrqEYOoRO",
					"type": "arrow"
				},
				{
					"id": "5rYB8Uw_Qw1Z5NjtE-Ii_",
					"type": "arrow"
				}
			],
			"updated": 1745111135266,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 358,
			"versionNonce": 142161767,
			"isDeleted": false,
			"id": "o5ouD0yF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 243.40589685830435,
			"y": -8.691016068045712,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 168.559814453125,
			"height": 25,
			"seed": 161188617,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111135266,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Exit (Unmounting)",
			"rawText": "Exit (Unmounting)",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "AlkB-gdZlAU6e-3WVIYoQ",
			"originalText": "Exit (Unmounting)",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "arrow",
			"version": 251,
			"versionNonce": 2079976135,
			"isDeleted": false,
			"id": "u61zjkQZVpnWobbGj0nHY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -301.09387185845594,
			"y": -163.39319206054162,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 6.8095020027548685,
			"height": 108.19451570865485,
			"seed": 563427145,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111135266,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "exjRsR1I5-QDSzCB-513H",
				"gap": 11.302759835855795,
				"focus": 0.05790328656061745
			},
			"endBinding": {
				"elementId": "SPnRvN5O-24umwObDE-vB",
				"gap": 10.417891434780472,
				"focus": -0.08652879437585062
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					6.8095020027548685,
					108.19451570865485
				]
			]
		},
		{
			"type": "arrow",
			"version": 345,
			"versionNonce": 1037923271,
			"isDeleted": false,
			"id": "d5GmR41pJn5QlDXKe1DOH",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -226.97178633501994,
			"y": -223.7235059570441,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 506.7985841634665,
			"height": 182.12350723109773,
			"seed": 182054247,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111135266,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "exjRsR1I5-QDSzCB-513H",
				"gap": 17.7238168169944,
				"focus": 0.4013883933488208
			},
			"endBinding": {
				"elementId": "AlkB-gdZlAU6e-3WVIYoQ",
				"gap": 10.1841487111802,
				"focus": 0.17639782506725593
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					217.00463701297372,
					36.57383701438724
				],
				[
					506.7985841634665,
					182.12350723109773
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1550,
			"versionNonce": 1586189511,
			"isDeleted": false,
			"id": "MPN6--RyhlkF0tD-mJYYQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 632.2253811938169,
			"y": -169.4354713692931,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 486.39748152166555,
			"height": 291.1034089559642,
			"seed": 88238505,
			"groupIds": [
				"ieHqCmRJkaDfNDhPfBPI9",
				"7bcdk0g2OmIl45za2s3v3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "5rYB8Uw_Qw1Z5NjtE-Ii_",
					"type": "arrow"
				}
			],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1331,
			"versionNonce": 571899689,
			"isDeleted": false,
			"id": "5-DDl5ymulaVWe7NUzQxf",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 628.1344182181551,
			"y": -128.67586082753706,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 490.04153672408853,
			"height": 0,
			"seed": 309939337,
			"groupIds": [
				"ieHqCmRJkaDfNDhPfBPI9",
				"7bcdk0g2OmIl45za2s3v3"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					490.04153672408853,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1151,
			"versionNonce": 267592679,
			"isDeleted": false,
			"id": "LQaJJq5DYlSBktZCJ5Rij",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 649.2953192089069,
			"y": -153.18884582061838,
			"strokeColor": "#000000",
			"backgroundColor": "#fa5252",
			"width": 19.02458890727497,
			"height": 19.02458890727497,
			"seed": 1620104041,
			"groupIds": [
				"ieHqCmRJkaDfNDhPfBPI9",
				"7bcdk0g2OmIl45za2s3v3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1196,
			"versionNonce": 1999548937,
			"isDeleted": false,
			"id": "8qkpum1SPwh9MiFAS-kx2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 688.3287836420488,
			"y": -153.18884582061838,
			"strokeColor": "#000000",
			"backgroundColor": "#fab005",
			"width": 19.02458890727497,
			"height": 19.02458890727497,
			"seed": 1406434889,
			"groupIds": [
				"ieHqCmRJkaDfNDhPfBPI9",
				"7bcdk0g2OmIl45za2s3v3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1254,
			"versionNonce": 1574178567,
			"isDeleted": false,
			"id": "ZD-qq6o0wKj0kUM_0s2sj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 729.0765353644656,
			"y": -151.47455853134346,
			"strokeColor": "#000000",
			"backgroundColor": "#40c057",
			"width": 19.02458890727497,
			"height": 19.02458890727497,
			"seed": 991939881,
			"groupIds": [
				"ieHqCmRJkaDfNDhPfBPI9",
				"7bcdk0g2OmIl45za2s3v3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1533,
			"versionNonce": 612206825,
			"isDeleted": false,
			"id": "KiALCw692XR04MlhhNUtd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 90,
			"angle": 0,
			"x": 790.0343730530149,
			"y": -90.42046400857913,
			"strokeColor": "#000000",
			"backgroundColor": "#04aaf7",
			"width": 162.48338819591544,
			"height": 162.48338819591544,
			"seed": 2111717385,
			"groupIds": [
				"ieHqCmRJkaDfNDhPfBPI9",
				"7bcdk0g2OmIl45za2s3v3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2151,
			"versionNonce": 313169447,
			"isDeleted": false,
			"id": "4VSm8fUo5FUChIzchbjJp",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 893.0243305294421,
			"y": -28.712243119723155,
			"strokeColor": "#087f5b",
			"backgroundColor": "#40c057",
			"width": 107.35644172137093,
			"height": 92.96015034464317,
			"seed": 168515305,
			"groupIds": [
				"ieHqCmRJkaDfNDhPfBPI9",
				"7bcdk0g2OmIl45za2s3v3"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-6.9624253173282264,
					-1.5770496828768925
				],
				[
					-28.80053995070944,
					-23.85370127029282
				],
				[
					-43.198212006169676,
					-16.53592680037457
				],
				[
					-47.967992932518385,
					9.02679483755474
				],
				[
					-42.86048241988136,
					25.63530551454704
				],
				[
					-66.27293650934502,
					33.79769236692656
				],
				[
					-65.43121046351891,
					51.89087324746409
				],
				[
					-47.0898960081687,
					50.77572096124574
				],
				[
					-33.071520257309345,
					36.04779254207737
				],
				[
					-13.768975440984933,
					67.95830411694203
				],
				[
					-1.5795352958713418,
					69.10644907435034
				],
				[
					-14.366497016725814,
					18.258144236486885
				],
				[
					5.273777385886872,
					16.535926800374455
				],
				[
					12.028369111653062,
					22.31624279284376
				],
				[
					35.12907281377366,
					22.31624279284376
				],
				[
					41.0835052120259,
					2.4150635311001643
				],
				[
					16.055144948167566,
					4.223061912306329
				],
				[
					20.866492592828653,
					-21.907133670089188
				],
				[
					9.404470018182241,
					-20.330083987212294
				],
				[
					-0.9040761232948957,
					-3.5104202146046513
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1570,
			"versionNonce": 864977865,
			"isDeleted": false,
			"id": "h7D2aQxYd8Q9VUdI-0maw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 90,
			"angle": 0,
			"x": 794.0624452264212,
			"y": -10.689598506975528,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 160.10591314200414,
			"height": 0,
			"seed": 36868553,
			"groupIds": [
				"ieHqCmRJkaDfNDhPfBPI9",
				"7bcdk0g2OmIl45za2s3v3"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					160.10591314200414,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3777,
			"versionNonce": 1969436999,
			"isDeleted": false,
			"id": "iaWZBp7Y9686zrxUQyWdD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 90,
			"angle": 0,
			"x": 813.4421830440883,
			"y": -69.39378074838243,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 111.51132848177924,
			"height": 21.722160953214146,
			"seed": 728723625,
			"groupIds": [
				"ieHqCmRJkaDfNDhPfBPI9",
				"7bcdk0g2OmIl45za2s3v3"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					2.9378447001938053,
					8.658816377526732
				],
				[
					15.607554318371525,
					15.923483760378533
				],
				[
					32.466587330354905,
					20.32292232827292
				],
				[
					58.87836810398671,
					20.723823404072384
				],
				[
					89.7000099217395,
					17.9228993567117
				],
				[
					107.70019705454055,
					7.73320090278254
				],
				[
					111.51132848177924,
					-0.9983375491417626
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1594,
			"versionNonce": 1887249065,
			"isDeleted": false,
			"id": "leUSJtecrdLt2X5hCyCbw",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 90,
			"angle": 0,
			"x": 844.1507737657314,
			"y": -95.67882153369652,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 59.06134515037869,
			"height": 170.47858784539633,
			"seed": 460157833,
			"groupIds": [
				"ieHqCmRJkaDfNDhPfBPI9",
				"7bcdk0g2OmIl45za2s3v3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 3982,
			"versionNonce": 995784807,
			"isDeleted": false,
			"id": "VtPR9lkWJSlacJgA5gHxI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 90,
			"angle": 0,
			"x": 819.2080016260038,
			"y": 51.31609286207441,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 111.51132848177924,
			"height": 22.425268851476588,
			"seed": 644356713,
			"groupIds": [
				"ieHqCmRJkaDfNDhPfBPI9",
				"7bcdk0g2OmIl45za2s3v3"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					15.607554318371525,
					-16.438898742519868
				],
				[
					32.466587330354905,
					-20.980739349128147
				],
				[
					58.87836810398671,
					-21.394616883090645
				],
				[
					89.7000099217395,
					-18.50303188241235
				],
				[
					107.70019705454055,
					-7.983510926969746
				],
				[
					111.51132848177924,
					1.0306519683859416
				]
			]
		},
		{
			"type": "text",
			"version": 815,
			"versionNonce": 401925513,
			"isDeleted": false,
			"id": "9oUw4zfd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 714.2260517108161,
			"y": 83.33536580536787,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 312.07958984375,
			"height": 25,
			"seed": 1576129959,
			"groupIds": [
				"7bcdk0g2OmIl45za2s3v3"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lo que el usuario finalmente ve",
			"rawText": "Lo que el usuario finalmente ve",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Lo que el usuario finalmente ve",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "arrow",
			"version": 1031,
			"versionNonce": 1427449095,
			"isDeleted": false,
			"id": "qghMXz80WXXGH6Lq3NMVl",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -654.7827072331492,
			"y": -0.9851239035607375,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 206.27518663322246,
			"height": 3.6217604398345,
			"seed": 1380032361,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111135266,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jq_XytFKDj197ea-ABRlY",
				"gap": 9.115630895864513,
				"focus": 0.013887243201037071
			},
			"endBinding": {
				"elementId": "SPnRvN5O-24umwObDE-vB",
				"gap": 1,
				"focus": -0.05041980389902405
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					206.27518663322246,
					-3.6217604398345
				]
			]
		},
		{
			"type": "arrow",
			"version": 290,
			"versionNonce": 2020240903,
			"isDeleted": false,
			"id": "ov8cvwNWA4mNGrqEYOoRO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -96.18685951920168,
			"y": -3.09773541215677,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 242.56013068521034,
			"height": 7.13666445003352,
			"seed": 803590087,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111135266,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "SPnRvN5O-24umwObDE-vB",
				"gap": 9.136639741000096,
				"focus": 0.028701426126580557
			},
			"endBinding": {
				"elementId": "AlkB-gdZlAU6e-3WVIYoQ",
				"gap": 10.220522248995735,
				"focus": -0.13822009176607153
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					242.56013068521034,
					7.13666445003352
				]
			]
		},
		{
			"type": "arrow",
			"version": 337,
			"versionNonce": 1999493191,
			"isDeleted": false,
			"id": "5rYB8Uw_Qw1Z5NjtE-Ii_",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 511.5259592149929,
			"y": -1.319062610447919,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffc9c9",
			"width": 111.76606001507366,
			"height": 2.193048287549288,
			"seed": 1939299017,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111135266,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "AlkB-gdZlAU6e-3WVIYoQ",
				"gap": 12.748144460263518,
				"focus": -0.03942000449631184
			},
			"endBinding": {
				"elementId": "MPN6--RyhlkF0tD-mJYYQ",
				"gap": 8.933361963750315,
				"focus": -0.10260775614886145
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					111.76606001507366,
					-2.193048287549288
				]
			]
		},
		{
			"type": "rectangle",
			"version": 708,
			"versionNonce": 536729417,
			"isDeleted": false,
			"id": "mOyStKHUmvK_UcIEtC2R6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -976.2521350371005,
			"y": 130.79797832000793,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 348.2557561035121,
			"height": 60,
			"seed": 394337799,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "sBdigUms"
				}
			],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 508,
			"versionNonce": 1222958535,
			"isDeleted": false,
			"id": "sBdigUms",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -962.4340714384695,
			"y": 135.79797832000793,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 320.61962890625,
			"height": 50,
			"seed": 917203271,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ejecutara todo el código dentro\nde la función",
			"rawText": "Ejecutara todo el código dentro de la función",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "mOyStKHUmvK_UcIEtC2R6",
			"originalText": "Ejecutara todo el código dentro de la función",
			"lineHeight": 1.25,
			"baseline": 42
		},
		{
			"type": "rectangle",
			"version": 854,
			"versionNonce": 1253443113,
			"isDeleted": false,
			"id": "axHFPSWlezViQSOhOePQO",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -974.0159688569947,
			"y": 222.67801792490394,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 348.2557561035121,
			"height": 85,
			"seed": 633149159,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "yLCKbZqj"
				}
			],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 405,
			"versionNonce": 1748208871,
			"isDeleted": false,
			"id": "yLCKbZqj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -962.337889389223,
			"y": 227.67801792490394,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 324.89959716796875,
			"height": 75,
			"seed": 1851174473,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Inicializara todos los valores ya\nsean Hooks o constantes y\nvariables",
			"rawText": "Inicializara todos los valores ya sean Hooks o constantes y variables",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "axHFPSWlezViQSOhOePQO",
			"originalText": "Inicializara todos los valores ya sean Hooks o constantes y variables",
			"lineHeight": 1.25,
			"baseline": 67
		},
		{
			"type": "rectangle",
			"version": 806,
			"versionNonce": 272980233,
			"isDeleted": false,
			"id": "G-LooFhzj3ysMbkzwwW_M",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -970.583602341993,
			"y": 476.9788307630637,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 348.2557561035121,
			"height": 60,
			"seed": 820666055,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "SwmSqmvD"
				},
				{
					"id": "pvCLzeGZ5qIXALa3fzHbp",
					"type": "arrow"
				},
				{
					"id": "4YAN5NhNoMG4SwCkZsVrZ",
					"type": "arrow"
				}
			],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 626,
			"versionNonce": 69163015,
			"isDeleted": false,
			"id": "SwmSqmvD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -814.8557105573268,
			"y": 494.4788307630637,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 36.79997253417969,
			"height": 25,
			"seed": 367062503,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "JSX",
			"rawText": "JSX",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "G-LooFhzj3ysMbkzwwW_M",
			"originalText": "JSX",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "rectangle",
			"version": 1471,
			"versionNonce": 1378308073,
			"isDeleted": false,
			"id": "A9dzKKX2hNpDAEC8rXD8K",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -943.1408917287142,
			"y": 785.647633679323,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 318.9037544412122,
			"height": 190.86030165342763,
			"seed": 766789321,
			"groupIds": [
				"CtqsAl9Iiff02imL_Vpqs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "pvCLzeGZ5qIXALa3fzHbp",
					"type": "arrow"
				},
				{
					"id": "Xzfuf6Z5d-_YI1MMFDGTv",
					"type": "arrow"
				}
			],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1231,
			"versionNonce": 1118093095,
			"isDeleted": false,
			"id": "j9FdhWaE_rGR4qdBOlEeK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -945.823108437849,
			"y": 812.3714415219602,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 321.2929585995235,
			"height": 0,
			"seed": 1190299049,
			"groupIds": [
				"CtqsAl9Iiff02imL_Vpqs"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					321.2929585995235,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1051,
			"versionNonce": 912747209,
			"isDeleted": false,
			"id": "2zeuqJSDPO33hBJI6OBax",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -931.9490835308987,
			"y": 796.2996417206971,
			"strokeColor": "#000000",
			"backgroundColor": "#fa5252",
			"width": 12.473363986693226,
			"height": 12.473363986693226,
			"seed": 1606805641,
			"groupIds": [
				"CtqsAl9Iiff02imL_Vpqs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1096,
			"versionNonce": 1446003271,
			"isDeleted": false,
			"id": "7wCgkHTUl5UDI70PaK8R6",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -906.357013609743,
			"y": 796.2996417206971,
			"strokeColor": "#000000",
			"backgroundColor": "#fab005",
			"width": 12.473363986693226,
			"height": 12.473363986693226,
			"seed": 300543849,
			"groupIds": [
				"CtqsAl9Iiff02imL_Vpqs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382918,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1154,
			"versionNonce": 362883497,
			"isDeleted": false,
			"id": "EmSRQAKf3DZLENad7gwL7",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -879.6409809348529,
			"y": 797.4236044744316,
			"strokeColor": "#000000",
			"backgroundColor": "#40c057",
			"width": 12.473363986693226,
			"height": 12.473363986693226,
			"seed": 866785865,
			"groupIds": [
				"CtqsAl9Iiff02imL_Vpqs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1433,
			"versionNonce": 1872650599,
			"isDeleted": false,
			"id": "H6neDTYkZSSipHjRux3pA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": -839.6743198397328,
			"y": 837.4533758178322,
			"strokeColor": "#000000",
			"backgroundColor": "#04aaf7",
			"width": 106.53131337748982,
			"height": 106.53131337748982,
			"seed": 1172433193,
			"groupIds": [
				"CtqsAl9Iiff02imL_Vpqs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2051,
			"versionNonce": 687869065,
			"isDeleted": false,
			"id": "pjSsCuS_9j0M03-HFUS3x",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -772.1495374205819,
			"y": 877.9120214090456,
			"strokeColor": "#087f5b",
			"backgroundColor": "#40c057",
			"width": 70.38764308829874,
			"height": 60.948796168891676,
			"seed": 570219529,
			"groupIds": [
				"CtqsAl9Iiff02imL_Vpqs"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.564874733245548,
					-1.0339836942337506
				],
				[
					-18.882910930134525,
					-15.639544161736483
				],
				[
					-28.322663083734188,
					-10.841686768827607
				],
				[
					-31.449942938300893,
					5.918366919296096
				],
				[
					-28.10123259294242,
					16.807642895808076
				],
				[
					-43.45147553921455,
					22.159265614499052
				],
				[
					-42.89960262370286,
					34.02195720273739
				],
				[
					-30.87422366224226,
					33.290813921040744
				],
				[
					-21.683154982916534,
					23.634531052715467
				],
				[
					-9.027550778433366,
					44.55647726742014
				],
				[
					-1.0356133723183036,
					45.309252007155195
				],
				[
					-9.41931241598804,
					11.970848878430083
				],
				[
					3.457722279286866,
					10.841686768827532
				],
				[
					7.8863320951221,
					14.631518217148741
				],
				[
					23.032177665278752,
					14.631518217148741
				],
				[
					26.9361675490842,
					1.5834227284081608
				],
				[
					10.526464869946981,
					2.768826628910465
				],
				[
					13.680997707995731,
					-14.363288137473107
				],
				[
					6.1659875128168045,
					-13.329304443239359
				],
				[
					-0.5927523907348936,
					-2.3015871352818342
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1470,
			"versionNonce": 1882954887,
			"isDeleted": false,
			"id": "gHuZh5F5BbxvK_jSQ6Uoh",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": -837.0333371289656,
			"y": 889.7284662927325,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 104.97253532129864,
			"height": 0,
			"seed": 1744204521,
			"groupIds": [
				"CtqsAl9Iiff02imL_Vpqs"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					104.97253532129864,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3677,
			"versionNonce": 2017432425,
			"isDeleted": false,
			"id": "oSh_gedOvhP3AZmwJvKph",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": -824.327121770272,
			"y": 851.2394016297776,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 73.11177106492208,
			"height": 14.242011823097258,
			"seed": 744107465,
			"groupIds": [
				"CtqsAl9Iiff02imL_Vpqs"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.9261812415763713,
					5.677103925726913
				],
				[
					10.233004608088477,
					10.440141957729674
				],
				[
					21.286534134906876,
					13.324608942110011
				],
				[
					38.603268637394685,
					13.58745746227916
				],
				[
					58.81130356178155,
					11.751047471393525
				],
				[
					70.6130243259113,
					5.070229381184973
				],
				[
					73.11177106492208,
					-0.6545543608180976
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1494,
			"versionNonce": 1539601319,
			"isDeleted": false,
			"id": "0DUOJQ6De1yM2x2XNBUpa",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": -804.1932081568762,
			"y": 834.0057634829409,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 38.72323650171919,
			"height": 111.77332075332971,
			"seed": 1715702953,
			"groupIds": [
				"CtqsAl9Iiff02imL_Vpqs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 3882,
			"versionNonce": 128663113,
			"isDeleted": false,
			"id": "kH0CDXqd28LY1rEGtxr1p",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": -820.5467954670861,
			"y": 930.3821467198018,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 73.11177106492208,
			"height": 14.703000535110512,
			"seed": 492703625,
			"groupIds": [
				"CtqsAl9Iiff02imL_Vpqs"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					10.233004608088477,
					-10.778070872135045
				],
				[
					21.286534134906876,
					-13.755902946819454
				],
				[
					38.603268637394685,
					-14.027259408301527
				],
				[
					58.81130356178155,
					-12.131408076758134
				],
				[
					70.6130243259113,
					-5.234343731115082
				],
				[
					73.11177106492208,
					0.6757411268089841
				]
			]
		},
		{
			"type": "text",
			"version": 544,
			"versionNonce": 174417607,
			"isDeleted": false,
			"id": "SUM0Z9n9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -815.802557779763,
			"y": 787.7378933207997,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 109.69987487792969,
			"height": 25,
			"seed": 1474639465,
			"groupIds": [
				"CtqsAl9Iiff02imL_Vpqs"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Virtual dom",
			"rawText": "Virtual dom",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Virtual dom",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "arrow",
			"version": 1639,
			"versionNonce": 274844071,
			"isDeleted": false,
			"id": "pvCLzeGZ5qIXALa3fzHbp",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -793.8735810343962,
			"y": 546.5319469479793,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 6.6158776008039695,
			"height": 223.11568673134377,
			"seed": 366626729,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "1vbSAKhB"
				}
			],
			"updated": 1745111135267,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "G-LooFhzj3ysMbkzwwW_M",
				"gap": 9.553116184915666,
				"focus": -0.008052369684508653
			},
			"endBinding": {
				"elementId": "A9dzKKX2hNpDAEC8rXD8K",
				"gap": 15.999999999999943,
				"focus": -0.0016301078089042298
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					6.6158776008039695,
					223.11568673134377
				]
			]
		},
		{
			"type": "text",
			"version": 127,
			"versionNonce": 448460263,
			"isDeleted": false,
			"id": "1vbSAKhB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -747.4395424427532,
			"y": 395.8999165156178,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 187.31979370117188,
			"height": 75,
			"seed": 625877193,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Va hacer un return\nhacia primero el\nvirtual DOM",
			"rawText": "Va hacer un return hacia primero el virtual DOM",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "pvCLzeGZ5qIXALa3fzHbp",
			"originalText": "Va hacer un return hacia primero el virtual DOM",
			"lineHeight": 1.25,
			"baseline": 67
		},
		{
			"type": "rectangle",
			"version": 1172,
			"versionNonce": 600940807,
			"isDeleted": false,
			"id": "ya3mDONbFaN1XjmVYlS0F",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -930.0189368575583,
			"y": 1311.4047653383768,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 306.943812543445,
			"height": 183.70241126620076,
			"seed": 1219842057,
			"groupIds": [
				"fGuwPmHBPm8xY0DvvZSJr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Xzfuf6Z5d-_YI1MMFDGTv",
					"type": "arrow"
				}
			],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 955,
			"versionNonce": 1952061161,
			"isDeleted": false,
			"id": "2GDc4CxlbgppRN_iuueY2",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -932.6005615995191,
			"y": 1337.1263423052906,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 309.24341367100686,
			"height": 0,
			"seed": 125855465,
			"groupIds": [
				"fGuwPmHBPm8xY0DvvZSJr"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					309.24341367100686,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 775,
			"versionNonce": 656795687,
			"isDeleted": false,
			"id": "1bG_QnCVOnCsu-9jOIOEi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -919.2468583553414,
			"y": 1321.6572879691994,
			"strokeColor": "#000000",
			"backgroundColor": "#fa5252",
			"width": 12.005571725006154,
			"height": 12.005571725006154,
			"seed": 780509641,
			"groupIds": [
				"fGuwPmHBPm8xY0DvvZSJr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 820,
			"versionNonce": 883511753,
			"isDeleted": false,
			"id": "7GySumXaqgv9m4P6EWnMI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -894.6145754076472,
			"y": 1321.6572879691994,
			"strokeColor": "#000000",
			"backgroundColor": "#fab005",
			"width": 12.005571725006154,
			"height": 12.005571725006154,
			"seed": 2061533353,
			"groupIds": [
				"fGuwPmHBPm8xY0DvvZSJr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 878,
			"versionNonce": 1118063431,
			"isDeleted": false,
			"id": "KACA61wTahEbkMgzib-sc",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -868.9004820140628,
			"y": 1322.7390984150893,
			"strokeColor": "#000000",
			"backgroundColor": "#40c057",
			"width": 12.005571725006154,
			"height": 12.005571725006154,
			"seed": 2050786185,
			"groupIds": [
				"fGuwPmHBPm8xY0DvvZSJr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1157,
			"versionNonce": 1628319913,
			"isDeleted": false,
			"id": "JXWXaRHTpu9i_ub86-Yoo",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 90,
			"angle": 0,
			"x": -830.4327024400553,
			"y": 1361.2676213950554,
			"strokeColor": "#000000",
			"backgroundColor": "#04aaf7",
			"width": 102.53603799880977,
			"height": 102.53603799880977,
			"seed": 2027235945,
			"groupIds": [
				"fGuwPmHBPm8xY0DvvZSJr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1774,
			"versionNonce": 581519975,
			"isDeleted": false,
			"id": "KxgvsNlhv59VEKRBcoKLF",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -765.4403219231883,
			"y": 1400.208934424973,
			"strokeColor": "#087f5b",
			"backgroundColor": "#40c057",
			"width": 67.74787447493796,
			"height": 58.66301542543174,
			"seed": 796259657,
			"groupIds": [
				"fGuwPmHBPm8xY0DvvZSJr"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.393676884929634,
					-0.9952058976915212
				],
				[
					-18.174739532212794,
					-15.05300970776092
				],
				[
					-27.260469866645735,
					-10.435087780815776
				],
				[
					-30.270466419157206,
					5.696408652895386
				],
				[
					-27.04734374909317,
					16.177300889253427
				],
				[
					-41.82190199050595,
					21.328220117054286
				],
				[
					-41.290726128298125,
					32.74602167132278
				],
				[
					-29.716338513520512,
					32.04229867253675
				],
				[
					-20.86996520341593,
					22.74815823886526
				],
				[
					-8.6889878694504,
					42.88546251182006
				],
				[
					-0.9967744574764874,
					43.61000571767081
				],
				[
					-9.066057154351094,
					11.521902589591805
				],
				[
					3.3280462971669706,
					10.435087780815703
				],
				[
					7.590568648218108,
					14.082788058546987
				],
				[
					22.168395088813142,
					14.082788058546987
				],
				[
					25.925972484432,
					1.524039157134287
				],
				[
					10.131687742114007,
					2.6649865042785534
				],
				[
					13.167915201401163,
					-13.824617490945066
				],
				[
					5.934742658002021,
					-12.829411593253546
				],
				[
					-0.5705222223714829,
					-2.2152700316815577
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1194,
			"versionNonce": 791950217,
			"isDeleted": false,
			"id": "Yga5q3rQTHSrPUvFTLMkW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 90,
			"angle": 0,
			"x": -827.8907652856163,
			"y": 1411.5822236785393,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 101.03571925745551,
			"height": 0,
			"seed": 830104617,
			"groupIds": [
				"fGuwPmHBPm8xY0DvvZSJr"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					101.03571925745551,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3401,
			"versionNonce": 872506759,
			"isDeleted": false,
			"id": "AEkqtjthxEIHJOBh5vdzy",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 90,
			"angle": 0,
			"x": -815.6610748825376,
			"y": 1374.5366258003355,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 70.36983867371683,
			"height": 13.707889438084834,
			"seed": 449705737,
			"groupIds": [
				"fGuwPmHBPm8xY0DvvZSJr"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8539430963272248,
					5.464193816787457
				],
				[
					9.849233207319713,
					10.04860222362502
				],
				[
					20.488218944468265,
					12.824892188892916
				],
				[
					37.155518827185894,
					13.077883023207454
				],
				[
					56.60568583626017,
					11.310344459784176
				],
				[
					67.96480317328387,
					4.880079067923286
				],
				[
					70.36983867371683,
					-0.6300064148773805
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1218,
			"versionNonce": 324459113,
			"isDeleted": false,
			"id": "2q2nVLMQrFisgkomPGC6v",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 90,
			"angle": 0,
			"x": -796.2822493909883,
			"y": 1357.9493058860471,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 37.27098750118435,
			"height": 107.58145282040844,
			"seed": 2112630249,
			"groupIds": [
				"fGuwPmHBPm8xY0DvvZSJr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 3606,
			"versionNonce": 367598759,
			"isDeleted": false,
			"id": "AuSsNXJpAYiV6llUVZrtS",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 90,
			"angle": 0,
			"x": -812.0225232756701,
			"y": 1450.7112570951335,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 70.36983867371683,
			"height": 14.151589553979596,
			"seed": 299927753,
			"groupIds": [
				"fGuwPmHBPm8xY0DvvZSJr"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.849233207319713,
					-10.373857689927073
				],
				[
					20.488218944468265,
					-13.240011246881462
				],
				[
					37.155518827185894,
					-13.50119094666753
				],
				[
					56.60568583626017,
					-11.676440288779716
				],
				[
					67.96480317328387,
					-5.038038588810404
				],
				[
					70.36983867371683,
					0.6503986073120648
				]
			]
		},
		{
			"type": "arrow",
			"version": 1414,
			"versionNonce": 1849795913,
			"isDeleted": false,
			"id": "Xzfuf6Z5d-_YI1MMFDGTv",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -785.4559219366071,
			"y": 991.4168773297923,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 6.74245061638419,
			"height": 315.4756776941447,
			"seed": 562004295,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "M9wLNIBm"
				}
			],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "A9dzKKX2hNpDAEC8rXD8K",
				"focus": 0.025543836844889624,
				"gap": 14.908941997041723
			},
			"endBinding": {
				"elementId": "BTXrImWq",
				"focus": -1.4378442085119718,
				"gap": 10.755793989625317
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					6.74245061638419,
					315.4756776941447
				]
			]
		},
		{
			"type": "text",
			"version": 16,
			"versionNonce": 1275916231,
			"isDeleted": false,
			"id": "M9wLNIBm",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -743.9679294776199,
			"y": 837.1639621513683,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 205.69973754882812,
			"height": 150,
			"seed": 1669178695,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lo pasara al virtual\nDOM para hacer las\nactualizaciones que\nsean necesarias\ncomparadas con el\nDOM",
			"rawText": "Lo pasara al virtual DOM para hacer las actualizaciones que sean necesarias comparadas con el DOM",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Xzfuf6Z5d-_YI1MMFDGTv",
			"originalText": "Lo pasara al virtual DOM para hacer las actualizaciones que sean necesarias comparadas con el DOM",
			"lineHeight": 1.25,
			"baseline": 142
		},
		{
			"type": "text",
			"version": 296,
			"versionNonce": 2068845609,
			"isDeleted": false,
			"id": "BTXrImWq",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -767.9576773305976,
			"y": 1314.2244436520223,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 45.439971923828125,
			"height": 25,
			"seed": 926694409,
			"groupIds": [
				"fGuwPmHBPm8xY0DvvZSJr"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Xzfuf6Z5d-_YI1MMFDGTv",
					"type": "arrow"
				}
			],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "DOM",
			"rawText": "DOM",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "DOM",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "rectangle",
			"version": 475,
			"versionNonce": 814309095,
			"isDeleted": false,
			"id": "68TpT98Umye9qZerXHj4G",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1060.9131926153168,
			"y": 103.78138401541617,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 511.26068192891626,
			"height": 247.40395494660265,
			"seed": 481340487,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "fwCluyowI4xTZCV66wM17",
					"type": "arrow"
				},
				{
					"id": "4YAN5NhNoMG4SwCkZsVrZ",
					"type": "arrow"
				},
				{
					"id": "SDyjQ2Ct-kJpP9IkFdTYs",
					"type": "arrow"
				}
			],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "diamond",
			"version": 788,
			"versionNonce": 1343773129,
			"isDeleted": false,
			"id": "psg6rUe32j9YpNJDZbU-I",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -605.8170781453302,
			"y": 1824.3217210132757,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 321.9048754167385,
			"height": 335.6762044288769,
			"seed": 1839356265,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "wK9S6uE6"
				},
				{
					"id": "fwCluyowI4xTZCV66wM17",
					"type": "arrow"
				},
				{
					"id": "EUMrKHGd-h_6roMWE5Mmj",
					"type": "arrow"
				},
				{
					"id": "xY3lRLeIufE70mCu9Xekb",
					"type": "arrow"
				}
			],
			"updated": 1745111164549,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 757,
			"versionNonce": 1808721959,
			"isDeleted": false,
			"id": "wK9S6uE6",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -514.6007775040363,
			"y": 1929.740772120495,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 139.51983642578125,
			"height": 125,
			"seed": 991597225,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745110129852,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Programa\ntodos los\nhooks una vez\nhecha esta\nsecuencia",
			"rawText": "Programa todos los hooks una vez hecha esta secuencia",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "psg6rUe32j9YpNJDZbU-I",
			"originalText": "Programa todos los hooks una vez hecha esta secuencia",
			"lineHeight": 1.25,
			"baseline": 117
		},
		{
			"type": "arrow",
			"version": 3075,
			"versionNonce": 1797699335,
			"isDeleted": false,
			"id": "fwCluyowI4xTZCV66wM17",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1074.5406843691894,
			"y": 264.92154044758024,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 807.9352146187422,
			"height": 1780.1296288362805,
			"seed": 961490025,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "dfnvHAAB"
				}
			],
			"updated": 1745111135268,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "68TpT98Umye9qZerXHj4G",
				"focus": 0.7712193937537848,
				"gap": 13.627491753872619
			},
			"endBinding": {
				"elementId": "psg6rUe32j9YpNJDZbU-I",
				"gap": 28.558281157682416,
				"focus": -0.40546572792508995
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-328.0578843320618,
					604.3350781308167
				],
				[
					-177.67255684381007,
					1713.578458594834
				],
				[
					479.8773302866804,
					1780.1296288362805
				]
			]
		},
		{
			"type": "text",
			"version": 144,
			"versionNonce": 154013991,
			"isDeleted": false,
			"id": "dfnvHAAB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1470.4529873067495,
			"y": 1953.4999990424144,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 468.7994689941406,
			"height": 50,
			"seed": 2042364873,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ejecuta todo lo que se haya dejado dentro de\nuseEffect",
			"rawText": "Ejecuta todo lo que se haya dejado dentro de useEffect",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "fwCluyowI4xTZCV66wM17",
			"originalText": "Ejecuta todo lo que se haya dejado dentro de useEffect",
			"lineHeight": 1.25,
			"baseline": 42
		},
		{
			"type": "arrow",
			"version": 469,
			"versionNonce": 1014680551,
			"isDeleted": false,
			"id": "4YAN5NhNoMG4SwCkZsVrZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -809.2912264470997,
			"y": 367.1853389620188,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 5.443167246219332,
			"height": 101.39384412463528,
			"seed": 126955559,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "icxqX7Dh"
				}
			],
			"updated": 1745111135267,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "68TpT98Umye9qZerXHj4G",
				"gap": 16,
				"focus": 0.04387846754426986
			},
			"endBinding": {
				"elementId": "G-LooFhzj3ysMbkzwwW_M",
				"gap": 8.399647676409586,
				"focus": -0.030334357770531454
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					5.443167246219332,
					101.39384412463528
				]
			]
		},
		{
			"type": "text",
			"version": 22,
			"versionNonce": 1673483335,
			"isDeleted": false,
			"id": "icxqX7Dh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -728.0247416912384,
			"y": 388.41429741515077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 131.85984802246094,
			"height": 25,
			"seed": 1943051847,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ejecuta todo",
			"rawText": "Ejecuta todo",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "4YAN5NhNoMG4SwCkZsVrZ",
			"originalText": "Ejecuta todo",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "arrow",
			"version": 1362,
			"versionNonce": 795360807,
			"isDeleted": false,
			"id": "EUMrKHGd-h_6roMWE5Mmj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -555.9771235860852,
			"y": 1911.512866016785,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 317.60321993461014,
			"height": 383.8816543832909,
			"seed": 1210183529,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "orw28LGb"
				}
			],
			"updated": 1745111135268,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "psg6rUe32j9YpNJDZbU-I",
				"gap": 19.84717107314836,
				"focus": 0.11647047539146672
			},
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-283.65192066341694,
					-155.97513444810534
				],
				[
					-317.60321993461014,
					-383.8816543832909
				]
			]
		},
		{
			"type": "text",
			"version": 194,
			"versionNonce": 1568355175,
			"isDeleted": false,
			"id": "orw28LGb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1645.3442068224865,
			"y": 1176.9213572252108,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 221.4397430419922,
			"height": 125,
			"seed": 336774121,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lo que ocurra\ndespués en el\nuseEffet se\nrenderizara de manera\nsincrona",
			"rawText": "Lo que ocurra después en el useEffet se renderizara de manera sincrona",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "EUMrKHGd-h_6roMWE5Mmj",
			"originalText": "Lo que ocurra después en el useEffet se renderizara de manera sincrona",
			"lineHeight": 1.25,
			"baseline": 117
		},
		{
			"type": "rectangle",
			"version": 717,
			"versionNonce": 831609481,
			"isDeleted": false,
			"id": "kM4inuC6jg5HfIrLKF63M",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1546.792296379493,
			"y": 2244.373590664853,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 433.8871645085661,
			"height": 118.91728747910929,
			"seed": 224588169,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "RN0e1dzZ"
				},
				{
					"id": "L8idZYeSp_DsV4yNK9AJD",
					"type": "arrow"
				}
			],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1101,
			"versionNonce": 1856908935,
			"isDeleted": false,
			"id": "RN0e1dzZ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1530.368458998257,
			"y": 2278.8322344044077,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 401.03948974609375,
			"height": 50,
			"seed": 2029901929,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ya que useEffect se ejecutara después\ndel renderizado del componente",
			"rawText": "Ya que useEffect se ejecutara después del renderizado del componente",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "kM4inuC6jg5HfIrLKF63M",
			"originalText": "Ya que useEffect se ejecutara después del renderizado del componente",
			"lineHeight": 1.25,
			"baseline": 42
		},
		{
			"type": "rectangle",
			"version": 900,
			"versionNonce": 1031217513,
			"isDeleted": false,
			"id": "C366ojlmlxlSSGCh1xJKg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1541.9331797928485,
			"y": 2724.8285395084085,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 433.8871645085661,
			"height": 118.91728747910929,
			"seed": 1113121609,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "N9EbiLSF"
				},
				{
					"id": "L8idZYeSp_DsV4yNK9AJD",
					"type": "arrow"
				}
			],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 1181,
			"versionNonce": 1377093031,
			"isDeleted": false,
			"id": "N9EbiLSF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1408.3894998823155,
			"y": 2771.787183247963,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#b2f2bb",
			"width": 166.7998046875,
			"height": 25,
			"seed": 97489449,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "useLayoutEffect",
			"rawText": "useLayoutEffect",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "C366ojlmlxlSSGCh1xJKg",
			"originalText": "useLayoutEffect",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "arrow",
			"version": 2064,
			"versionNonce": 1914275271,
			"isDeleted": false,
			"id": "L8idZYeSp_DsV4yNK9AJD",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -1331.8814339167507,
			"y": 2376.9870185499226,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 8.766693133693025,
			"height": 335.9908636466871,
			"seed": 1213031689,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "PnjwDwUM"
				}
			],
			"updated": 1745111135269,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "kM4inuC6jg5HfIrLKF63M",
				"gap": 13.69614040596025,
				"focus": 0.018039218373973764
			},
			"endBinding": {
				"elementId": "C366ojlmlxlSSGCh1xJKg",
				"gap": 11.850657311798841,
				"focus": 0.017096334068189112
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					8.766693133693025,
					335.9908636466871
				]
			]
		},
		{
			"type": "text",
			"version": 186,
			"versionNonce": 920352967,
			"isDeleted": false,
			"id": "PnjwDwUM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -2074.770962791316,
			"y": 1108.3637585076315,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 219.87974548339844,
			"height": 125,
			"seed": 1699601385,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Si necesitamos que se\nejecute algo antes de\nque se muestre en el\nnavegador\nnecesitaríamos usar",
			"rawText": "Si necesitamos que se ejecute algo antes de que se muestre en el navegador necesitaríamos usar",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "L8idZYeSp_DsV4yNK9AJD",
			"originalText": "Si necesitamos que se ejecute algo antes de que se muestre en el navegador necesitaríamos usar",
			"lineHeight": 1.25,
			"baseline": 117
		},
		{
			"type": "text",
			"version": 354,
			"versionNonce": 1363843881,
			"isDeleted": false,
			"id": "90lmH2PW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -1571.4790778120343,
			"y": 2255.0782438199813,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 9.999984741210938,
			"height": 25,
			"seed": 67695,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": " ",
			"rawText": " ",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": " ",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "rectangle",
			"version": 798,
			"versionNonce": 849266663,
			"isDeleted": false,
			"id": "RlmwQrz1OwggHk8Pq_91I",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -448.43271693400004,
			"y": 127.2744474596056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 348.2557561035121,
			"height": 60,
			"seed": 587270345,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "ekaHAf46"
				}
			],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 625,
			"versionNonce": 1635733001,
			"isDeleted": false,
			"id": "ekaHAf46",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -434.614653335369,
			"y": 132.2744474596056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 320.61962890625,
			"height": 50,
			"seed": 962004905,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ejecutara todo el código dentro\nde la función denuevo",
			"rawText": "Ejecutara todo el código dentro de la función denuevo",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "RlmwQrz1OwggHk8Pq_91I",
			"originalText": "Ejecutara todo el código dentro de la función denuevo",
			"lineHeight": 1.25,
			"baseline": 42
		},
		{
			"type": "arrow",
			"version": 124,
			"versionNonce": 1382097031,
			"isDeleted": false,
			"id": "SDyjQ2Ct-kJpP9IkFdTYs",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -806.6583900507064,
			"y": 44.337757576998335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 2.422073424693963,
			"height": 54.63770003868189,
			"seed": 1333901193,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111135265,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jq_XytFKDj197ea-ABRlY",
				"gap": 5.42531672434319,
				"focus": 0.03887777022308537
			},
			"endBinding": {
				"elementId": "68TpT98Umye9qZerXHj4G",
				"gap": 4.805926399735938,
				"focus": 0.025824937930628688
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					2.422073424693963,
					54.63770003868189
				]
			]
		},
		{
			"type": "rectangle",
			"version": 963,
			"versionNonce": 844801257,
			"isDeleted": false,
			"id": "BPoPPNE7NVo6W7PwPKkrj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -441.3916220776632,
			"y": 224.94351497422326,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 348.2557561035121,
			"height": 85,
			"seed": 289199399,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "a1npfOsd"
				}
			],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 588,
			"versionNonce": 834484775,
			"isDeleted": false,
			"id": "a1npfOsd",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -407.9535786206337,
			"y": 229.94351497422326,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 281.3796691894531,
			"height": 75,
			"seed": 89495623,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Volverá a calcular todos los\nvalores ya sean Hooks o\nconstantes y variables",
			"rawText": "Volverá a calcular todos los valores ya sean Hooks o constantes y variables",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "BPoPPNE7NVo6W7PwPKkrj",
			"originalText": "Volverá a calcular todos los valores ya sean Hooks o constantes y variables",
			"lineHeight": 1.25,
			"baseline": 67
		},
		{
			"type": "rectangle",
			"version": 522,
			"versionNonce": 1063788489,
			"isDeleted": false,
			"id": "Tpc7Pd9MnXWe7NU4FpLWh",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -507.92544955941196,
			"y": 104.38556281071703,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 511.26068192891626,
			"height": 247.40395494660265,
			"seed": 52781961,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "g3PfQ9YGBQVKho_5FDTL9",
					"type": "arrow"
				},
				{
					"id": "rQVWrxe8s5JGsS8gAeb1V",
					"type": "arrow"
				}
			],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "arrow",
			"version": 49,
			"versionNonce": 895674759,
			"isDeleted": false,
			"id": "g3PfQ9YGBQVKho_5FDTL9",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -270.92487154533114,
			"y": 36.30282436124052,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 3.213989514885043,
			"height": 61.06559792554224,
			"seed": 575761607,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111135266,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "SPnRvN5O-24umwObDE-vB",
				"gap": 10.63394138490591,
				"focus": -0.01779174658557169
			},
			"endBinding": {
				"elementId": "Tpc7Pd9MnXWe7NU4FpLWh",
				"gap": 7.017140523934245,
				"focus": -0.0325618549947433
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					3.213989514885043,
					61.06559792554224
				]
			]
		},
		{
			"type": "rectangle",
			"version": 1568,
			"versionNonce": 113458857,
			"isDeleted": false,
			"id": "GPvBVCiVkFeFZl3YgPCeP",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -385.3311181713128,
			"y": 781.1010243281063,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 318.9037544412122,
			"height": 190.86030165342763,
			"seed": 394750601,
			"groupIds": [
				"wW5l4u03nlJtx3d4V43jd"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "tsUj_FUnUNeVHACZkF2Pu",
					"type": "arrow"
				},
				{
					"id": "BN1PKhUfqJgXV0ajYU0D2",
					"type": "arrow"
				}
			],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1328,
			"versionNonce": 689183847,
			"isDeleted": false,
			"id": "QPXX5OLh37J_siCT2-t_W",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -388.0133348804476,
			"y": 807.8248321707434,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 321.2929585995235,
			"height": 0,
			"seed": 439038313,
			"groupIds": [
				"wW5l4u03nlJtx3d4V43jd"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					321.2929585995235,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1148,
			"versionNonce": 924287369,
			"isDeleted": false,
			"id": "W0SIQrNEiIlh41EwHsUWA",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -374.13930997349723,
			"y": 791.7530323694804,
			"strokeColor": "#000000",
			"backgroundColor": "#fa5252",
			"width": 12.473363986693226,
			"height": 12.473363986693226,
			"seed": 1718819913,
			"groupIds": [
				"wW5l4u03nlJtx3d4V43jd"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1193,
			"versionNonce": 155318151,
			"isDeleted": false,
			"id": "rZ6a4BBZLoN3jrAR-sX8l",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -348.54724005234164,
			"y": 791.7530323694804,
			"strokeColor": "#000000",
			"backgroundColor": "#fab005",
			"width": 12.473363986693226,
			"height": 12.473363986693226,
			"seed": 2084219689,
			"groupIds": [
				"wW5l4u03nlJtx3d4V43jd"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1251,
			"versionNonce": 497051753,
			"isDeleted": false,
			"id": "67_4tQAv-YcePDBrHdYIS",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -321.8312073774515,
			"y": 792.8769951232149,
			"strokeColor": "#000000",
			"backgroundColor": "#40c057",
			"width": 12.473363986693226,
			"height": 12.473363986693226,
			"seed": 1408065033,
			"groupIds": [
				"wW5l4u03nlJtx3d4V43jd"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1530,
			"versionNonce": 1497853607,
			"isDeleted": false,
			"id": "hg5PGRe8hW2VezrDaIOwI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": -281.8645462823314,
			"y": 832.9067664666155,
			"strokeColor": "#000000",
			"backgroundColor": "#04aaf7",
			"width": 106.53131337748982,
			"height": 106.53131337748982,
			"seed": 1283896553,
			"groupIds": [
				"wW5l4u03nlJtx3d4V43jd"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2148,
			"versionNonce": 1412002633,
			"isDeleted": false,
			"id": "BHhuIvH94A-R7W7WAKPUz",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -214.33976386318034,
			"y": 873.3654120578288,
			"strokeColor": "#087f5b",
			"backgroundColor": "#40c057",
			"width": 70.38764308829874,
			"height": 60.948796168891676,
			"seed": 1502752713,
			"groupIds": [
				"wW5l4u03nlJtx3d4V43jd"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.564874733245548,
					-1.0339836942337506
				],
				[
					-18.882910930134525,
					-15.639544161736483
				],
				[
					-28.322663083734188,
					-10.841686768827607
				],
				[
					-31.449942938300893,
					5.918366919296096
				],
				[
					-28.10123259294242,
					16.807642895808076
				],
				[
					-43.45147553921455,
					22.159265614499052
				],
				[
					-42.89960262370286,
					34.02195720273739
				],
				[
					-30.87422366224226,
					33.290813921040744
				],
				[
					-21.683154982916534,
					23.634531052715467
				],
				[
					-9.027550778433366,
					44.55647726742014
				],
				[
					-1.0356133723183036,
					45.309252007155195
				],
				[
					-9.41931241598804,
					11.970848878430083
				],
				[
					3.457722279286866,
					10.841686768827532
				],
				[
					7.8863320951221,
					14.631518217148741
				],
				[
					23.032177665278752,
					14.631518217148741
				],
				[
					26.9361675490842,
					1.5834227284081608
				],
				[
					10.526464869946981,
					2.768826628910465
				],
				[
					13.680997707995731,
					-14.363288137473107
				],
				[
					6.1659875128168045,
					-13.329304443239359
				],
				[
					-0.5927523907348936,
					-2.3015871352818342
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1567,
			"versionNonce": 1943077319,
			"isDeleted": false,
			"id": "PwwZmP_7mq3LEnWovuIMU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": -279.2235635715641,
			"y": 885.1818569415158,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 104.97253532129864,
			"height": 0,
			"seed": 1898663593,
			"groupIds": [
				"wW5l4u03nlJtx3d4V43jd"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					104.97253532129864,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3774,
			"versionNonce": 789455401,
			"isDeleted": false,
			"id": "QwD03daDSLLZ8jVqVjTHK",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": -266.5173482128706,
			"y": 846.6927922785609,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 73.11177106492208,
			"height": 14.242011823097258,
			"seed": 972919177,
			"groupIds": [
				"wW5l4u03nlJtx3d4V43jd"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.9261812415763713,
					5.677103925726913
				],
				[
					10.233004608088477,
					10.440141957729674
				],
				[
					21.286534134906876,
					13.324608942110011
				],
				[
					38.603268637394685,
					13.58745746227916
				],
				[
					58.81130356178155,
					11.751047471393525
				],
				[
					70.6130243259113,
					5.070229381184973
				],
				[
					73.11177106492208,
					-0.6545543608180976
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1591,
			"versionNonce": 704327911,
			"isDeleted": false,
			"id": "eL6YoY42yH2RegjtCvXmU",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": -246.38343459947475,
			"y": 829.4591541317242,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 38.72323650171919,
			"height": 111.77332075332971,
			"seed": 2034530409,
			"groupIds": [
				"wW5l4u03nlJtx3d4V43jd"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 3979,
			"versionNonce": 1798960393,
			"isDeleted": false,
			"id": "vM0HOs5qYds9stl1pszHa",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": -262.7370219096846,
			"y": 925.835537368585,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 73.11177106492208,
			"height": 14.703000535110512,
			"seed": 1087079241,
			"groupIds": [
				"wW5l4u03nlJtx3d4V43jd"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					10.233004608088477,
					-10.778070872135045
				],
				[
					21.286534134906876,
					-13.755902946819454
				],
				[
					38.603268637394685,
					-14.027259408301527
				],
				[
					58.81130356178155,
					-12.131408076758134
				],
				[
					70.6130243259113,
					-5.234343731115082
				],
				[
					73.11177106492208,
					0.6757411268089841
				]
			]
		},
		{
			"type": "text",
			"version": 641,
			"versionNonce": 1968339975,
			"isDeleted": false,
			"id": "ZMjEXRch",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -257.9927842223616,
			"y": 783.191283969583,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 109.69987487792969,
			"height": 25,
			"seed": 1559114281,
			"groupIds": [
				"wW5l4u03nlJtx3d4V43jd"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Virtual dom",
			"rawText": "Virtual dom",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Virtual dom",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "arrow",
			"version": 1878,
			"versionNonce": 373948423,
			"isDeleted": false,
			"id": "tsUj_FUnUNeVHACZkF2Pu",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -236.06380747699492,
			"y": 541.9853375967625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 6.615877600804055,
			"height": 223.11568673134389,
			"seed": 43517193,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "XfMSAn0K"
				}
			],
			"updated": 1745111135269,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "DtQAGCmnnjwMb1Uf2UtKC",
				"gap": 8.944316062476219,
				"focus": -0.020098657849955782
			},
			"endBinding": {
				"elementId": "GPvBVCiVkFeFZl3YgPCeP",
				"gap": 15.999999999999943,
				"focus": -0.001630107808904774
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					6.615877600804055,
					223.11568673134389
				]
			]
		},
		{
			"type": "text",
			"version": 130,
			"versionNonce": 1775461159,
			"isDeleted": false,
			"id": "XfMSAn0K",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -220.03016950133224,
			"y": 200.53745113392097,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 187.31979370117188,
			"height": 75,
			"seed": 1027898345,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382919,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Va hacer un return\nhacia primero el\nvirtual DOM",
			"rawText": "Va hacer un return hacia primero el virtual DOM",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "tsUj_FUnUNeVHACZkF2Pu",
			"originalText": "Va hacer un return hacia primero el virtual DOM",
			"lineHeight": 1.25,
			"baseline": 67
		},
		{
			"type": "rectangle",
			"version": 1270,
			"versionNonce": 956922921,
			"isDeleted": false,
			"id": "eJLu0VUe-oL9e0-yN9qOJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -374.06885756097415,
			"y": 1306.85815598716,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 306.943812543445,
			"height": 183.70241126620076,
			"seed": 486479561,
			"groupIds": [
				"IOrb8dZ3ipfXF_IaOfms4"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "BN1PKhUfqJgXV0ajYU0D2",
					"type": "arrow"
				},
				{
					"id": "xY3lRLeIufE70mCu9Xekb",
					"type": "arrow"
				}
			],
			"updated": 1745111131673,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1053,
			"versionNonce": 244663785,
			"isDeleted": false,
			"id": "xcG4fnqt7_NyuXzaUWCV4",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -376.6504823029351,
			"y": 1332.5797329540737,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 309.24341367100686,
			"height": 0,
			"seed": 610489769,
			"groupIds": [
				"IOrb8dZ3ipfXF_IaOfms4"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111131674,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					309.24341367100686,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 873,
			"versionNonce": 1571201225,
			"isDeleted": false,
			"id": "cvwoFZNp1khzdwIEu4SL8",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -363.29677905875735,
			"y": 1317.1106786179826,
			"strokeColor": "#000000",
			"backgroundColor": "#fa5252",
			"width": 12.005571725006154,
			"height": 12.005571725006154,
			"seed": 1989982345,
			"groupIds": [
				"IOrb8dZ3ipfXF_IaOfms4"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111131674,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 918,
			"versionNonce": 998875049,
			"isDeleted": false,
			"id": "vYu6CTTnibvsM8lpVTfXl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -338.66449611106316,
			"y": 1317.1106786179826,
			"strokeColor": "#000000",
			"backgroundColor": "#fab005",
			"width": 12.005571725006154,
			"height": 12.005571725006154,
			"seed": 1164361577,
			"groupIds": [
				"IOrb8dZ3ipfXF_IaOfms4"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111131674,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 976,
			"versionNonce": 644465289,
			"isDeleted": false,
			"id": "GrFcyn7meAO_vahnDZetE",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -312.9504027174788,
			"y": 1318.1924890638725,
			"strokeColor": "#000000",
			"backgroundColor": "#40c057",
			"width": 12.005571725006154,
			"height": 12.005571725006154,
			"seed": 2131552841,
			"groupIds": [
				"IOrb8dZ3ipfXF_IaOfms4"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111131674,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1255,
			"versionNonce": 1258457449,
			"isDeleted": false,
			"id": "Nss2Cgr9TkHjEUst-4dNg",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 90,
			"angle": 0,
			"x": -274.4826231434712,
			"y": 1356.7210120438385,
			"strokeColor": "#000000",
			"backgroundColor": "#04aaf7",
			"width": 102.53603799880977,
			"height": 102.53603799880977,
			"seed": 1013627177,
			"groupIds": [
				"IOrb8dZ3ipfXF_IaOfms4"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111131674,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1872,
			"versionNonce": 849310793,
			"isDeleted": false,
			"id": "WSFNbTFBqwbqjSz4GTEhJ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": -209.4902426266043,
			"y": 1395.6623250737562,
			"strokeColor": "#087f5b",
			"backgroundColor": "#40c057",
			"width": 67.74787447493796,
			"height": 58.66301542543174,
			"seed": 1860938761,
			"groupIds": [
				"IOrb8dZ3ipfXF_IaOfms4"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111131674,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.393676884929634,
					-0.9952058976915212
				],
				[
					-18.174739532212794,
					-15.05300970776092
				],
				[
					-27.260469866645735,
					-10.435087780815776
				],
				[
					-30.270466419157206,
					5.696408652895386
				],
				[
					-27.04734374909317,
					16.177300889253427
				],
				[
					-41.82190199050595,
					21.328220117054286
				],
				[
					-41.290726128298125,
					32.74602167132278
				],
				[
					-29.716338513520512,
					32.04229867253675
				],
				[
					-20.86996520341593,
					22.74815823886526
				],
				[
					-8.6889878694504,
					42.88546251182006
				],
				[
					-0.9967744574764874,
					43.61000571767081
				],
				[
					-9.066057154351094,
					11.521902589591805
				],
				[
					3.3280462971669706,
					10.435087780815703
				],
				[
					7.590568648218108,
					14.082788058546987
				],
				[
					22.168395088813142,
					14.082788058546987
				],
				[
					25.925972484432,
					1.524039157134287
				],
				[
					10.131687742114007,
					2.6649865042785534
				],
				[
					13.167915201401163,
					-13.824617490945066
				],
				[
					5.934742658002021,
					-12.829411593253546
				],
				[
					-0.5705222223714829,
					-2.2152700316815577
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1292,
			"versionNonce": 823919401,
			"isDeleted": false,
			"id": "XD9HUkNRvGUmO26U6k8Ns",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 90,
			"angle": 0,
			"x": -271.9406859890322,
			"y": 1407.0356143273225,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 101.03571925745551,
			"height": 0,
			"seed": 1317749481,
			"groupIds": [
				"IOrb8dZ3ipfXF_IaOfms4"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111131674,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					101.03571925745551,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3499,
			"versionNonce": 316913161,
			"isDeleted": false,
			"id": "6FgiT24QbDSd_TX0sWEMl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 90,
			"angle": 0,
			"x": -259.7109955859536,
			"y": 1369.9900164491187,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 70.36983867371683,
			"height": 13.707889438084834,
			"seed": 131399113,
			"groupIds": [
				"IOrb8dZ3ipfXF_IaOfms4"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111131674,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8539430963272248,
					5.464193816787457
				],
				[
					9.849233207319713,
					10.04860222362502
				],
				[
					20.488218944468265,
					12.824892188892916
				],
				[
					37.155518827185894,
					13.077883023207454
				],
				[
					56.60568583626017,
					11.310344459784176
				],
				[
					67.96480317328387,
					4.880079067923286
				],
				[
					70.36983867371683,
					-0.6300064148773805
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1316,
			"versionNonce": 183635177,
			"isDeleted": false,
			"id": "Lzvq3GuL_LYabdv5ouN5P",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 90,
			"angle": 0,
			"x": -240.3321700944042,
			"y": 1353.4026965348303,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 37.27098750118435,
			"height": 107.58145282040844,
			"seed": 702831785,
			"groupIds": [
				"IOrb8dZ3ipfXF_IaOfms4"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111131674,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 3704,
			"versionNonce": 1624410057,
			"isDeleted": false,
			"id": "cYpJFmsjnezCzWMszbhy0",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 90,
			"angle": 0,
			"x": -256.07244397908596,
			"y": 1446.164647743917,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 70.36983867371683,
			"height": 14.151589553979596,
			"seed": 1415896969,
			"groupIds": [
				"IOrb8dZ3ipfXF_IaOfms4"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111131674,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.849233207319713,
					-10.373857689927073
				],
				[
					20.488218944468265,
					-13.240011246881462
				],
				[
					37.155518827185894,
					-13.50119094666753
				],
				[
					56.60568583626017,
					-11.676440288779716
				],
				[
					67.96480317328387,
					-5.038038588810404
				],
				[
					70.36983867371683,
					0.6503986073120648
				]
			]
		},
		{
			"type": "arrow",
			"version": 1799,
			"versionNonce": 998851145,
			"isDeleted": false,
			"id": "BN1PKhUfqJgXV0ajYU0D2",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -227.64614837920556,
			"y": 986.8702679785755,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.160733256980166,
			"height": 320.37806978730066,
			"seed": 630326889,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "dCTOHF2A"
				}
			],
			"updated": 1745111133227,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "GPvBVCiVkFeFZl3YgPCeP",
				"focus": 0.022015642225037664,
				"gap": 14.908941997041495
			},
			"endBinding": {
				"elementId": "5vcXEpsE",
				"focus": -1.437844208511967,
				"gap": 10.47781708821185
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					5.160733256980166,
					320.37806978730066
				]
			]
		},
		{
			"type": "text",
			"version": 19,
			"versionNonce": 580754441,
			"isDeleted": false,
			"id": "dCTOHF2A",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -220.73919581958097,
			"y": 654.1023769971343,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 205.69973754882812,
			"height": 150,
			"seed": 1748455753,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382920,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lo pasara al virtual\nDOM para hacer las\nactualizaciones que\nsean necesarias\ncomparadas con el\nDOM",
			"rawText": "Lo pasara al virtual DOM para hacer las actualizaciones que sean necesarias comparadas con el DOM",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "BN1PKhUfqJgXV0ajYU0D2",
			"originalText": "Lo pasara al virtual DOM para hacer las actualizaciones que sean necesarias comparadas con el DOM",
			"lineHeight": 1.25,
			"baseline": 142
		},
		{
			"type": "text",
			"version": 394,
			"versionNonce": 1587586729,
			"isDeleted": false,
			"id": "5vcXEpsE",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -212.00759803401354,
			"y": 1309.6778343008054,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 45.439971923828125,
			"height": 25,
			"seed": 28327977,
			"groupIds": [
				"IOrb8dZ3ipfXF_IaOfms4"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "BN1PKhUfqJgXV0ajYU0D2",
					"type": "arrow"
				}
			],
			"updated": 1745111131674,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "DOM",
			"rawText": "DOM",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "DOM",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "arrow",
			"version": 566,
			"versionNonce": 198240839,
			"isDeleted": false,
			"id": "rQVWrxe8s5JGsS8gAeb1V",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -251.48127162587855,
			"y": 362.6387296108021,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 5.443036623793205,
			"height": 101.39384412463522,
			"seed": 535319305,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "0kE5YOzv"
				}
			],
			"updated": 1745111135270,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "Tpc7Pd9MnXWe7NU4FpLWh",
				"gap": 10.849211853482359,
				"focus": 0.0244371588821937
			},
			"endBinding": {
				"elementId": "DtQAGCmnnjwMb1Uf2UtKC",
				"gap": 9.008447798848977,
				"focus": -0.01825423936132294
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					5.443036623793205,
					101.39384412463522
				]
			]
		},
		{
			"type": "text",
			"version": 25,
			"versionNonce": 2054196263,
			"isDeleted": false,
			"id": "0kE5YOzv",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -208.30408129936586,
			"y": -14.67007815539381,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 131.85984802246094,
			"height": 25,
			"seed": 660277737,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382920,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ejecuta todo",
			"rawText": "Ejecuta todo",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "rQVWrxe8s5JGsS8gAeb1V",
			"originalText": "Ejecuta todo",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "rectangle",
			"version": 845,
			"versionNonce": 197848521,
			"isDeleted": false,
			"id": "DtQAGCmnnjwMb1Uf2UtKC",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -414.8640870792715,
			"y": 473.0410215342863,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 348.2557561035121,
			"height": 60,
			"seed": 1657890279,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "BvlXUKKM"
				},
				{
					"id": "tsUj_FUnUNeVHACZkF2Pu",
					"type": "arrow"
				},
				{
					"id": "rQVWrxe8s5JGsS8gAeb1V",
					"type": "arrow"
				}
			],
			"updated": 1745109382920,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 664,
			"versionNonce": 486174535,
			"isDeleted": false,
			"id": "BvlXUKKM",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -259.1361952946053,
			"y": 490.5410215342863,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 36.79997253417969,
			"height": 25,
			"seed": 2140803335,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382920,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "JSX",
			"rawText": "JSX",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "DtQAGCmnnjwMb1Uf2UtKC",
			"originalText": "JSX",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "arrow",
			"version": 212,
			"versionNonce": 2083250503,
			"isDeleted": false,
			"id": "xY3lRLeIufE70mCu9Xekb",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -358.6919319322309,
			"y": 1891.5256963827812,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 139.20504672455445,
			"height": 377.36755848626785,
			"seed": 1952009513,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "Brw2Wg5w"
				}
			],
			"updated": 1745111135268,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "psg6rUe32j9YpNJDZbU-I",
				"gap": 15.680762660244483,
				"focus": -0.19777702107841372
			},
			"endBinding": {
				"elementId": "eJLu0VUe-oL9e0-yN9qOJ",
				"focus": -0.009185225189682825,
				"gap": 23.59757064315272
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					138.50187615792072,
					-108.39292688082082
				],
				[
					139.20504672455445,
					-377.36755848626785
				]
			]
		},
		{
			"type": "text",
			"version": 210,
			"versionNonce": 35555719,
			"isDeleted": false,
			"id": "Brw2Wg5w",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -318.055362972824,
			"y": 1712.1473298571577,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 203.75973510742188,
			"height": 150,
			"seed": 874460871,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109382920,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Acá también va a\nvolver a re-ejecutar\nuseEffect por si el\ncaso que poseemos\nalguna dependencia\nque fue actualizada",
			"rawText": "Acá también va a volver a re-ejecutar useEffect por si el caso que poseemos alguna dependencia que fue actualizada",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "xY3lRLeIufE70mCu9Xekb",
			"originalText": "Acá también va a volver a re-ejecutar useEffect por si el caso que poseemos alguna dependencia que fue actualizada",
			"lineHeight": 1.25,
			"baseline": 142
		},
		{
			"type": "rectangle",
			"version": 132,
			"versionNonce": 434863625,
			"isDeleted": false,
			"id": "nGUshS8VAxQWlK6IXlxdB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 89.3268970270426,
			"y": 101.60085880537923,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 502.26803500856056,
			"height": 216.8463587862757,
			"seed": 1386362279,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "Uz7xpOWU"
				},
				{
					"id": "u__PJz1zvzkCIKhMigZwN",
					"type": "arrow"
				}
			],
			"updated": 1745109542377,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 276,
			"versionNonce": 1841353961,
			"isDeleted": false,
			"id": "Uz7xpOWU",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 97.93117515144007,
			"y": 160.02403819851708,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 485.0594787597656,
			"height": 100,
			"seed": 716273735,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109542377,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Esto sucede cuando ya no es necesario tener un\ncomponente en pantalla, por ejemplo navegaciones\nde pantalla o cambia un valor del componente\ncual hace que no se renderize",
			"rawText": "Esto sucede cuando ya no es necesario tener un componente en pantalla, por ejemplo navegaciones de pantalla o cambia un valor del componente cual hace que no se renderize",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "nGUshS8VAxQWlK6IXlxdB",
			"originalText": "Esto sucede cuando ya no es necesario tener un componente en pantalla, por ejemplo navegaciones de pantalla o cambia un valor del componente cual hace que no se renderize",
			"lineHeight": 1.25,
			"baseline": 92
		},
		{
			"type": "arrow",
			"version": 562,
			"versionNonce": 913444551,
			"isDeleted": false,
			"id": "u__PJz1zvzkCIKhMigZwN",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 335.4850836321584,
			"y": 333.27436383968495,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 8.720884562632477,
			"height": 263.7299668171919,
			"seed": 1840241097,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "jEOjZSeB"
				}
			],
			"updated": 1745111135270,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "nGUshS8VAxQWlK6IXlxdB",
				"gap": 14.827146248030033,
				"focus": 0.035534834771843285
			},
			"endBinding": {
				"elementId": "71FZQzp_s-Zae-DeF2X1W",
				"gap": 14.560054781360066,
				"focus": -0.01133494637490292
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					8.720884562632477,
					263.7299668171919
				]
			]
		},
		{
			"type": "text",
			"version": 145,
			"versionNonce": 916972327,
			"isDeleted": false,
			"id": "jEOjZSeB",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 232.57899008546917,
			"y": 396.80475600624544,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 215.11973571777344,
			"height": 125,
			"seed": 1416288393,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109655838,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lo primero que hará\nes liberar todos los\nvalores de la memoria\n(useState, useMemo,\nconst, vars...)",
			"rawText": "Lo primero que hará es liberar todos los valores de la memoria  \n(useState, useMemo, const, vars...)",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "u__PJz1zvzkCIKhMigZwN",
			"originalText": "Lo primero que hará es liberar todos los valores de la memoria  \n(useState, useMemo, const, vars...)",
			"lineHeight": 1.25,
			"baseline": 117
		},
		{
			"type": "diamond",
			"version": 142,
			"versionNonce": 1687734727,
			"isDeleted": false,
			"id": "71FZQzp_s-Zae-DeF2X1W",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 154.19542790104413,
			"y": 608.9656642316414,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 396.6248987447023,
			"height": 342.2406257875932,
			"seed": 875490279,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"id": "u__PJz1zvzkCIKhMigZwN",
					"type": "arrow"
				},
				{
					"type": "text",
					"id": "ocRbLPNj"
				},
				{
					"id": "BBWpgA9lmrJqaQlxOIjVJ",
					"type": "arrow"
				},
				{
					"id": "ru5Ox8EmkStJUVNUEQ29k",
					"type": "arrow"
				}
			],
			"updated": 1745111145795,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 210,
			"versionNonce": 44072935,
			"isDeleted": false,
			"id": "ocRbLPNj",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 263.14175268487594,
			"y": 730.0258206785397,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 178.4197998046875,
			"height": 100,
			"seed": 368213289,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745110127557,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ejecutaran\ncleanups functions\ncomo las del\nuseEffect",
			"rawText": "Ejecutaran cleanups functions como las del useEffect",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "71FZQzp_s-Zae-DeF2X1W",
			"originalText": "Ejecutaran cleanups functions como las del useEffect",
			"lineHeight": 1.25,
			"baseline": 92
		},
		{
			"type": "rectangle",
			"version": 117,
			"versionNonce": 1807887369,
			"isDeleted": false,
			"id": "jN7RfamBWqo0bykfhgROg",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 544.3615408157809,
			"y": 575.8257496092232,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 474.4672293779562,
			"height": 77.84228384102789,
			"seed": 1361019911,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "pRokJwHo"
				},
				{
					"id": "BBWpgA9lmrJqaQlxOIjVJ",
					"type": "arrow"
				}
			],
			"updated": 1745109771785,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 174,
			"versionNonce": 283118727,
			"isDeleted": false,
			"id": "pRokJwHo",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 554.0454118524153,
			"y": 589.7468915297371,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 455.0994873046875,
			"height": 50,
			"seed": 637858055,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745109768824,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Si tenemos funciones de limpieza un ejemplo es\nel return de useEffect",
			"rawText": "Si tenemos funciones de limpieza un ejemplo es el return de useEffect",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "jN7RfamBWqo0bykfhgROg",
			"originalText": "Si tenemos funciones de limpieza un ejemplo es el return de useEffect",
			"lineHeight": 1.25,
			"baseline": 42
		},
		{
			"type": "arrow",
			"version": 64,
			"versionNonce": 1658079495,
			"isDeleted": false,
			"id": "BBWpgA9lmrJqaQlxOIjVJ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 444.27853760270784,
			"y": 661.0815597820401,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 87.10925024604671,
			"height": 57.45500454221258,
			"seed": 1085134535,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111135271,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "71FZQzp_s-Zae-DeF2X1W",
				"gap": 20.495891950400676,
				"focus": 0.327254329157839
			},
			"endBinding": {
				"elementId": "jN7RfamBWqo0bykfhgROg",
				"gap": 12.973752967026428,
				"focus": 0.28571454333534657
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					12.973752967026371,
					-57.455004542212464
				],
				[
					87.10925024604671,
					-57.45500454221258
				]
			]
		},
		{
			"type": "diamond",
			"version": 371,
			"versionNonce": 1588856233,
			"isDeleted": false,
			"id": "ffXQlnAnImHIOSMYoVBrF",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -641.3002555341653,
			"y": 984.148343884242,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 290.98190285752224,
			"height": 320,
			"seed": 2135505737,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [
				{
					"type": "text",
					"id": "pTgVSlwP"
				}
			],
			"updated": 1745110143547,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 506,
			"versionNonce": 56060041,
			"isDeleted": false,
			"id": "pTgVSlwP",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -557.0047081034762,
			"y": 1081.648343884242,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 121.89985656738281,
			"height": 125,
			"seed": 1928653353,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745110143547,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Ejecutaran\ncleanups\nfunctions\ncomo las del\nuseEffect",
			"rawText": "Ejecutaran cleanups functions como las del useEffect",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "ffXQlnAnImHIOSMYoVBrF",
			"originalText": "Ejecutaran cleanups functions como las del useEffect",
			"lineHeight": 1.25,
			"baseline": 117
		},
		{
			"type": "rectangle",
			"version": 1701,
			"versionNonce": 1184814151,
			"isDeleted": false,
			"id": "09vM3yH2Vr3R0pCriyme-",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 218.28128793518755,
			"y": 1377.2584581587255,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 318.9037544412122,
			"height": 190.86030165342763,
			"seed": 1967136553,
			"groupIds": [
				"3_wpp_DItDXPaZOJjxccG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "dlhNPWNVKL-bu0ccfQvqi",
					"type": "arrow"
				},
				{
					"id": "Ma0OxsmexVivPauB01jI3",
					"type": "arrow"
				}
			],
			"updated": 1745111141302,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1461,
			"versionNonce": 1461994919,
			"isDeleted": false,
			"id": "Z7EfGDmPPB8XKjqOmJc87",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 215.59907122605279,
			"y": 1403.9822660013626,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 321.2929585995235,
			"height": 0,
			"seed": 1948537353,
			"groupIds": [
				"3_wpp_DItDXPaZOJjxccG"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					321.2929585995235,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1281,
			"versionNonce": 1845164231,
			"isDeleted": false,
			"id": "1n1CWZFHm2HTl-bdX66El",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 229.47309613300314,
			"y": 1387.9104662000998,
			"strokeColor": "#000000",
			"backgroundColor": "#fa5252",
			"width": 12.473363986693226,
			"height": 12.473363986693226,
			"seed": 834611433,
			"groupIds": [
				"3_wpp_DItDXPaZOJjxccG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1326,
			"versionNonce": 1506691047,
			"isDeleted": false,
			"id": "ipWeksLMIMbdDWs-kFdKQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 255.06516605415874,
			"y": 1387.9104662000998,
			"strokeColor": "#000000",
			"backgroundColor": "#fab005",
			"width": 12.473363986693226,
			"height": 12.473363986693226,
			"seed": 1738286025,
			"groupIds": [
				"3_wpp_DItDXPaZOJjxccG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1384,
			"versionNonce": 145404679,
			"isDeleted": false,
			"id": "WGIzT8iCzDG2CO579VsvI",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 281.78119872904887,
			"y": 1389.034428953834,
			"strokeColor": "#000000",
			"backgroundColor": "#40c057",
			"width": 12.473363986693226,
			"height": 12.473363986693226,
			"seed": 299287209,
			"groupIds": [
				"3_wpp_DItDXPaZOJjxccG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1663,
			"versionNonce": 1930213927,
			"isDeleted": false,
			"id": "qa9Ay-VBLxaR_Zjz9C1ps",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": 321.747859824169,
			"y": 1429.0642002972347,
			"strokeColor": "#000000",
			"backgroundColor": "#04aaf7",
			"width": 106.53131337748982,
			"height": 106.53131337748982,
			"seed": 488277385,
			"groupIds": [
				"3_wpp_DItDXPaZOJjxccG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2281,
			"versionNonce": 1306582343,
			"isDeleted": false,
			"id": "Rs-foWInf4nNRuyMdQN6H",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 389.27264224332004,
			"y": 1469.5228458884483,
			"strokeColor": "#087f5b",
			"backgroundColor": "#40c057",
			"width": 70.38764308829874,
			"height": 60.948796168891676,
			"seed": 1419963497,
			"groupIds": [
				"3_wpp_DItDXPaZOJjxccG"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.564874733245548,
					-1.0339836942337506
				],
				[
					-18.882910930134525,
					-15.639544161736483
				],
				[
					-28.322663083734188,
					-10.841686768827607
				],
				[
					-31.449942938300893,
					5.918366919296096
				],
				[
					-28.10123259294242,
					16.807642895808076
				],
				[
					-43.45147553921455,
					22.159265614499052
				],
				[
					-42.89960262370286,
					34.02195720273739
				],
				[
					-30.87422366224226,
					33.290813921040744
				],
				[
					-21.683154982916534,
					23.634531052715467
				],
				[
					-9.027550778433366,
					44.55647726742014
				],
				[
					-1.0356133723183036,
					45.309252007155195
				],
				[
					-9.41931241598804,
					11.970848878430083
				],
				[
					3.457722279286866,
					10.841686768827532
				],
				[
					7.8863320951221,
					14.631518217148741
				],
				[
					23.032177665278752,
					14.631518217148741
				],
				[
					26.9361675490842,
					1.5834227284081608
				],
				[
					10.526464869946981,
					2.768826628910465
				],
				[
					13.680997707995731,
					-14.363288137473107
				],
				[
					6.1659875128168045,
					-13.329304443239359
				],
				[
					-0.5927523907348936,
					-2.3015871352818342
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1700,
			"versionNonce": 2089000039,
			"isDeleted": false,
			"id": "fwUcf-Sr7ei7taOsKI8f3",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": 324.38884253493626,
			"y": 1481.3392907721352,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 104.97253532129864,
			"height": 0,
			"seed": 272332617,
			"groupIds": [
				"3_wpp_DItDXPaZOJjxccG"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					104.97253532129864,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3907,
			"versionNonce": 1119975303,
			"isDeleted": false,
			"id": "3XKv9BrUttc1OkCsue7hm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": 337.09505789362976,
			"y": 1442.85022610918,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 73.11177106492208,
			"height": 14.242011823097258,
			"seed": 574596649,
			"groupIds": [
				"3_wpp_DItDXPaZOJjxccG"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.9261812415763713,
					5.677103925726913
				],
				[
					10.233004608088477,
					10.440141957729674
				],
				[
					21.286534134906876,
					13.324608942110011
				],
				[
					38.603268637394685,
					13.58745746227916
				],
				[
					58.81130356178155,
					11.751047471393525
				],
				[
					70.6130243259113,
					5.070229381184973
				],
				[
					73.11177106492208,
					-0.6545543608180976
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1724,
			"versionNonce": 920055463,
			"isDeleted": false,
			"id": "BDpFJkDkOoF1GqvD2f_Bk",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": 357.2289715070256,
			"y": 1425.6165879623434,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 38.72323650171919,
			"height": 111.77332075332971,
			"seed": 94042377,
			"groupIds": [
				"3_wpp_DItDXPaZOJjxccG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 4112,
			"versionNonce": 1936753095,
			"isDeleted": false,
			"id": "LeKj4hO4wx92Qbc1zojzD",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 90,
			"angle": 0,
			"x": 340.8753841968158,
			"y": 1521.9929711992042,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 73.11177106492208,
			"height": 14.703000535110512,
			"seed": 1271459817,
			"groupIds": [
				"3_wpp_DItDXPaZOJjxccG"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					10.233004608088477,
					-10.778070872135045
				],
				[
					21.286534134906876,
					-13.755902946819454
				],
				[
					38.603268637394685,
					-14.027259408301527
				],
				[
					58.81130356178155,
					-12.131408076758134
				],
				[
					70.6130243259113,
					-5.234343731115082
				],
				[
					73.11177106492208,
					0.6757411268089841
				]
			]
		},
		{
			"type": "text",
			"version": 774,
			"versionNonce": 162181351,
			"isDeleted": false,
			"id": "1iQz0Ec5",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 345.6196218841388,
			"y": 1379.3487178002022,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 109.69987487792969,
			"height": 25,
			"seed": 1255475913,
			"groupIds": [
				"3_wpp_DItDXPaZOJjxccG"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Virtual dom",
			"rawText": "Virtual dom",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Virtual dom",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "arrow",
			"version": 2337,
			"versionNonce": 868684041,
			"isDeleted": false,
			"id": "dlhNPWNVKL-bu0ccfQvqi",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 367.5485986295055,
			"y": 1138.1427714273818,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 6.615877600804026,
			"height": 223.11568673134366,
			"seed": 190499241,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "lVcUrzr7"
				}
			],
			"updated": 1745111141546,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "cqIX2Zh4tH-7uineYAL0l",
				"focus": -0.02009865784995545,
				"gap": 8.944316062476219
			},
			"endBinding": {
				"elementId": "09vM3yH2Vr3R0pCriyme-",
				"focus": -0.0016301078089043988,
				"gap": 16
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					6.615877600804026,
					223.11568673134366
				]
			]
		},
		{
			"type": "text",
			"version": 133,
			"versionNonce": 820848039,
			"isDeleted": false,
			"id": "lVcUrzr7",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 19.7209522051957,
			"y": 414.96379302620403,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 187.31979370117188,
			"height": 75,
			"seed": 1988471945,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111134867,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Va hacer un return\nhacia primero el\nvirtual DOM",
			"rawText": "Va hacer un return hacia primero el virtual DOM",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "dlhNPWNVKL-bu0ccfQvqi",
			"originalText": "Va hacer un return hacia primero el virtual DOM",
			"lineHeight": 1.25,
			"baseline": 67
		},
		{
			"type": "rectangle",
			"version": 1405,
			"versionNonce": 1230780585,
			"isDeleted": false,
			"id": "WY8zZzlqJF3fUhtLEWwbQ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 229.54354854552622,
			"y": 1903.0155898177793,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 306.943812543445,
			"height": 183.70241126620076,
			"seed": 1141977961,
			"groupIds": [
				"s6hTmMEkd9Kgdr9YLsd3Q"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Ma0OxsmexVivPauB01jI3",
					"type": "arrow"
				}
			],
			"updated": 1745111164549,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 1186,
			"versionNonce": 1539958343,
			"isDeleted": false,
			"id": "y4sHXQSB1MoVDZ8OW1dfT",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 226.9619238035653,
			"y": 1928.737166784693,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 309.24341367100686,
			"height": 0,
			"seed": 675864137,
			"groupIds": [
				"s6hTmMEkd9Kgdr9YLsd3Q"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					309.24341367100686,
					0
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1006,
			"versionNonce": 1516471655,
			"isDeleted": false,
			"id": "k0chrc1PZ4fE5qcxNNH3l",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 240.31562704774302,
			"y": 1913.2681124486019,
			"strokeColor": "#000000",
			"backgroundColor": "#fa5252",
			"width": 12.005571725006154,
			"height": 12.005571725006154,
			"seed": 1107832105,
			"groupIds": [
				"s6hTmMEkd9Kgdr9YLsd3Q"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1051,
			"versionNonce": 247218311,
			"isDeleted": false,
			"id": "xn52EHXlTxXtB9kAjqlvp",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 264.9479099954372,
			"y": 1913.2681124486019,
			"strokeColor": "#000000",
			"backgroundColor": "#fab005",
			"width": 12.005571725006154,
			"height": 12.005571725006154,
			"seed": 1220190217,
			"groupIds": [
				"s6hTmMEkd9Kgdr9YLsd3Q"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1109,
			"versionNonce": 714119079,
			"isDeleted": false,
			"id": "4lhizY9PKLZOpHz1gwoZi",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 290.66200338902155,
			"y": 1914.3499228944918,
			"strokeColor": "#000000",
			"backgroundColor": "#40c057",
			"width": 12.005571725006154,
			"height": 12.005571725006154,
			"seed": 2052830953,
			"groupIds": [
				"s6hTmMEkd9Kgdr9YLsd3Q"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false
		},
		{
			"type": "ellipse",
			"version": 1388,
			"versionNonce": 1947011783,
			"isDeleted": false,
			"id": "KKYrNrAz6KxDnW5SsFd4w",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 90,
			"angle": 0,
			"x": 329.1297829630292,
			"y": 1952.8784458744578,
			"strokeColor": "#000000",
			"backgroundColor": "#04aaf7",
			"width": 102.53603799880977,
			"height": 102.53603799880977,
			"seed": 1232531913,
			"groupIds": [
				"s6hTmMEkd9Kgdr9YLsd3Q"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 2005,
			"versionNonce": 936253927,
			"isDeleted": false,
			"id": "A-rHrc-BMqVwWZBPRvFpW",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 100,
			"angle": 0,
			"x": 394.1221634798961,
			"y": 1991.8197589043755,
			"strokeColor": "#087f5b",
			"backgroundColor": "#40c057",
			"width": 67.74787447493796,
			"height": 58.66301542543174,
			"seed": 1260900521,
			"groupIds": [
				"s6hTmMEkd9Kgdr9YLsd3Q"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-4.393676884929634,
					-0.9952058976915212
				],
				[
					-18.174739532212794,
					-15.05300970776092
				],
				[
					-27.260469866645735,
					-10.435087780815776
				],
				[
					-30.270466419157206,
					5.696408652895386
				],
				[
					-27.04734374909317,
					16.177300889253427
				],
				[
					-41.82190199050595,
					21.328220117054286
				],
				[
					-41.290726128298125,
					32.74602167132278
				],
				[
					-29.716338513520512,
					32.04229867253675
				],
				[
					-20.86996520341593,
					22.74815823886526
				],
				[
					-8.6889878694504,
					42.88546251182006
				],
				[
					-0.9967744574764874,
					43.61000571767081
				],
				[
					-9.066057154351094,
					11.521902589591805
				],
				[
					3.3280462971669706,
					10.435087780815703
				],
				[
					7.590568648218108,
					14.082788058546987
				],
				[
					22.168395088813142,
					14.082788058546987
				],
				[
					25.925972484432,
					1.524039157134287
				],
				[
					10.131687742114007,
					2.6649865042785534
				],
				[
					13.167915201401163,
					-13.824617490945066
				],
				[
					5.934742658002021,
					-12.829411593253546
				],
				[
					-0.5705222223714829,
					-2.2152700316815577
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1425,
			"versionNonce": 2061518087,
			"isDeleted": false,
			"id": "1xyO8YnACozxvA6nOIzKy",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 90,
			"angle": 0,
			"x": 331.67172011746817,
			"y": 2003.1930481579418,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 101.03571925745551,
			"height": 0,
			"seed": 1696191369,
			"groupIds": [
				"s6hTmMEkd9Kgdr9YLsd3Q"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					101.03571925745551,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 3632,
			"versionNonce": 1824525351,
			"isDeleted": false,
			"id": "C0ynKWTpfLR3FuBDa3Rdj",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 90,
			"angle": 0,
			"x": 343.9014105205468,
			"y": 1966.147450279738,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 70.36983867371683,
			"height": 13.707889438084834,
			"seed": 998799977,
			"groupIds": [
				"s6hTmMEkd9Kgdr9YLsd3Q"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					1.8539430963272248,
					5.464193816787457
				],
				[
					9.849233207319713,
					10.04860222362502
				],
				[
					20.488218944468265,
					12.824892188892916
				],
				[
					37.155518827185894,
					13.077883023207454
				],
				[
					56.60568583626017,
					11.310344459784176
				],
				[
					67.96480317328387,
					4.880079067923286
				],
				[
					70.36983867371683,
					-0.6300064148773805
				]
			]
		},
		{
			"type": "ellipse",
			"version": 1449,
			"versionNonce": 425324359,
			"isDeleted": false,
			"id": "3OzsAcy1pO34mbeTh_Wkq",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 90,
			"angle": 0,
			"x": 363.28023601209617,
			"y": 1949.5601303654496,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 37.27098750118435,
			"height": 107.58145282040844,
			"seed": 1597982025,
			"groupIds": [
				"s6hTmMEkd9Kgdr9YLsd3Q"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 3837,
			"versionNonce": 1527410279,
			"isDeleted": false,
			"id": "t1HYJZSs7LEpw0nTvSQCb",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 0,
			"opacity": 90,
			"angle": 0,
			"x": 347.5399621274144,
			"y": 2042.3220815745362,
			"strokeColor": "#000000",
			"backgroundColor": "#99bcff",
			"width": 70.36983867371683,
			"height": 14.151589553979596,
			"seed": 999928873,
			"groupIds": [
				"s6hTmMEkd9Kgdr9YLsd3Q"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					9.849233207319713,
					-10.373857689927073
				],
				[
					20.488218944468265,
					-13.240011246881462
				],
				[
					37.155518827185894,
					-13.50119094666753
				],
				[
					56.60568583626017,
					-11.676440288779716
				],
				[
					67.96480317328387,
					-5.038038588810404
				],
				[
					70.36983867371683,
					0.6503986073120648
				]
			]
		},
		{
			"type": "arrow",
			"version": 2258,
			"versionNonce": 1054548681,
			"isDeleted": false,
			"id": "Ma0OxsmexVivPauB01jI3",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 375.9662577272948,
			"y": 1583.027701809195,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 5.160733256980166,
			"height": 320.37806978730066,
			"seed": 1149454089,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "mFB4y8wT"
				}
			],
			"updated": 1745111141546,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "09vM3yH2Vr3R0pCriyme-",
				"focus": 0.022015642225037345,
				"gap": 14.908941997041893
			},
			"endBinding": {
				"elementId": "rBCecqjY",
				"focus": -1.4378442085119665,
				"gap": 10.47781708821185
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					5.160733256980166,
					320.37806978730066
				]
			]
		},
		{
			"type": "text",
			"version": 22,
			"versionNonce": 1537726663,
			"isDeleted": false,
			"id": "mFB4y8wT",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 18.22106720724497,
			"y": 870.9799149359956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 205.69973754882812,
			"height": 150,
			"seed": 1685552617,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111134867,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Lo pasara al virtual\nDOM para hacer las\nactualizaciones que\nsean necesarias\ncomparadas con el\nDOM",
			"rawText": "Lo pasara al virtual DOM para hacer las actualizaciones que sean necesarias comparadas con el DOM",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "Ma0OxsmexVivPauB01jI3",
			"originalText": "Lo pasara al virtual DOM para hacer las actualizaciones que sean necesarias comparadas con el DOM",
			"lineHeight": 1.25,
			"baseline": 142
		},
		{
			"type": "text",
			"version": 527,
			"versionNonce": 2068922535,
			"isDeleted": false,
			"id": "rBCecqjY",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 391.60480807248683,
			"y": 1905.8352681314248,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 45.439971923828125,
			"height": 25,
			"seed": 713152713,
			"groupIds": [
				"s6hTmMEkd9Kgdr9YLsd3Q"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "Ma0OxsmexVivPauB01jI3",
					"type": "arrow"
				}
			],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "DOM",
			"rawText": "DOM",
			"textAlign": "center",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "DOM",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"type": "rectangle",
			"version": 979,
			"versionNonce": 482886663,
			"isDeleted": false,
			"id": "cqIX2Zh4tH-7uineYAL0l",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 188.7483190272289,
			"y": 1069.1984553649056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 348.2557561035121,
			"height": 60,
			"seed": 943577001,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"type": "text",
					"id": "hxKoD4fQ"
				},
				{
					"id": "dlhNPWNVKL-bu0ccfQvqi",
					"type": "arrow"
				},
				{
					"id": "ru5Ox8EmkStJUVNUEQ29k",
					"type": "arrow"
				}
			],
			"updated": 1745111145795,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 797,
			"versionNonce": 1226149383,
			"isDeleted": false,
			"id": "hxKoD4fQ",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 344.4762108118951,
			"y": 1086.6984553649056,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 36.79997253417969,
			"height": 25,
			"seed": 1876359817,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1745111141303,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "JSX",
			"rawText": "JSX",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "cqIX2Zh4tH-7uineYAL0l",
			"originalText": "JSX",
			"lineHeight": 1.25,
			"baseline": 17
		},
		{
			"id": "ru5Ox8EmkStJUVNUEQ29k",
			"type": "arrow",
			"x": 350.8666584104558,
			"y": 963.9015201828055,
			"width": 4.395419034090992,
			"height": 94.50361772017038,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1015215689,
			"version": 26,
			"versionNonce": 1049229543,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1745111145795,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					4.395419034090992,
					94.50361772017038
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "71FZQzp_s-Zae-DeF2X1W",
				"focus": 0.051386528110671625,
				"gap": 10.683822933367026
			},
			"endBinding": {
				"elementId": "cqIX2Zh4tH-7uineYAL0l",
				"focus": -0.03257004488392585,
				"gap": 10.793317461929746
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"id": "bggrXwhrdOb1096rL8g8p",
			"type": "arrow",
			"x": 203.61679157806952,
			"y": 2022.122117230861,
			"width": 520.8686967329547,
			"height": 186.809414950284,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"fillStyle": "hachure",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1299758793,
			"version": 355,
			"versionNonce": 1364877351,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1745111164549,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					-195.60036399147725,
					186.809414950284
				],
				[
					-520.8686967329547,
					30.76859907670405
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "WY8zZzlqJF3fUhtLEWwbQ",
				"focus": 0.6042999432333883,
				"gap": 25.92675696745667
			},
			"endBinding": {
				"elementId": "psg6rUe32j9YpNJDZbU-I",
				"focus": -0.0029117410847215434,
				"gap": 17.971510131136313
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		}
	],
	"appState": {
		"theme": "dark",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#a5d8ff",
		"currentItemFillStyle": "hachure",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 2,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "center",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1562.4628401888183,
		"scrollY": -89.66984338630698,
		"zoom": {
			"value": 0.44999999999999996
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"gridColor": {
			"Bold": "#C9C9C9FF",
			"Regular": "#EDEDEDFF"
		},
		"currentStrokeOptions": null,
		"previousGridSize": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true
		}
	},
	"files": {}
}
```
%%