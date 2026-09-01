<!doctype html>
<!--
 @license
 Copyright 2019 Google LLC. All Rights Reserved.
 SPDX-License-Identifier: Apache-2.0

 History: 
 v1.0  26 Dec 2025  Created
 v1.1. 28 Dec 2025  Tidy data formatting for easier scraping

 Source: https://jsfiddle.net/gh/get/library/pure/googlemaps/js-samples/tree/master/dist/samples/streetview-events/jsfiddle
-->

<html>
  <head>
    <title>Street View Demo</title>
    <!-- jsFiddle will insert css and js -->
    <style>
      #map {
        height: 100%;
      }

      /* 
      * Optional: Makes the sample page fill the window. 
      */
      html,
      body {
        height: 100%;
        margin: 0;
        padding: 0;
      }

      table, td {
        border: 1px solid;
        border-collapse: collapse;
      }

      td {
        padding: 5px;
      }  

      .table-spacing {
        margin-bottom: 5px; /* Adds 5px of space below each table */
      }

      #floating-panel {
        position: absolute;
        top: 10px;
        left: 25%;
        z-index: 5;
        background-color: #fff;
        padding: 5px;
        border: 1px solid #999;
        text-align: center;
        font-family: "Roboto", "sans-serif";
        line-height: 30px;
        padding-left: 10px;
      }

      #pano {
        width: 60%;
        height: 100%;
        float: left;
      }

      #floating-panel {
        width: 35%;
        height: 100%;
        float: right;
        text-align: left;
        overflow: auto;
        position: static;
        border: 0px solid #999;
      }
    </style>

  </head>

  <body>
    <div id="pano"></div>
    <div id="floating-panel">
      <table id="pov_table" class="table-spacing">
        <tr>
          <td><b>Position</b></td>
          <td id="position-cell">&nbsp;</td>
        </tr>
        <tr>
          <td><b>POV Heading</b></td>
          <td id="heading-cell">0.0</td>
        </tr>
        <tr>
          <td><b>POV Pitch</b></td>
          <td id="pitch-cell">0.0</td>
        </tr>
        <tr>
          <td><b>Pano ID</b></td>
          <td id="pano-cell">&nbsp;</td>
        </tr>
      </table>
      <table id="links_table" class="table-spacing">
      </table>
    </div>

    <!-- 
      The `defer` attribute causes the script to execute after the full HTML
      document has been parsed. For non-blocking uses, avoiding race conditions,
      and consistent behavior across browsers, consider loading using Promises. See
      https://developers.google.com/maps/documentation/javascript/load-maps-js-api
      for more information.
      -->
    <script
      src="https://maps.googleapis.com/maps/api/js?key=<your API key>&callback=initPano&v=weekly"
      defer
    ></script>
    <script>
      function initPano() {

        //const mylocation = { lat: 37.869, lng: -122.255 }; // Indoors Bancroft Hotel, Berkeley
        //const mylocation = { lat: 42.345573, lng: -71.0983264 }; // Outdoors 41, Jersey St, Boston, Massachusetts
        const mylocation = { lat: 42.345415183529354, lng: -71.09826342320486 }; // Outdoors 41, Jersey St, Boston, Massachusetts
        //const mylocation = { lat:36.9412716428490, lng: 140.9168353519920 }; // 07204-bldg-158309, pano_id: cTuWX6F-vccYl1Fe48uvPQ
        //const mylocation = { lat:36.9388736446420, lng:140.8731150136540 }; // 07204-bldg-157922, pano_id: cTuWX6F-vccYl1Fe48uvPQ
        //const mylocation = { lat:36.9443083934862, lng:140.9055448141970 }; // Aquamarine Fukushima, snap to indoor photosphere, 07204-bldg-160926, pano_id: 
        //const mylocation = { lat:36.94523512435817, lng:140.90614667124356 }; // Aquamarine Fukushima, outdoor carpark, 07204-bldg-160926, pano_id: K_GfVGm_Nh0XI4XEGOWE9A
        //const mylocation = { lat:36.9428714028443, lng: 140.8935470030150 }; // 07204-bldg-159152, snap to the wrong outdoor photosphere
        //const mylocation = { lat:36.94304766366964, lng: 140.89314458650665 };
         // const mylocation = { lat: 36.94834751200853, lng: 140.90639035874815 }; // junction near 07204-bldg-166786, pano_id: -Xnvqux2F4Z7c8C4ZGpavw
        const mylocation = { lat: 36.948296958284935, lng: 140.90637979088467 }; // junction near 07204-bldg-166786, pano_id: OVq6rHNatFZWmCgZ1itSWg

        const panorama = new google.maps.StreetViewPanorama(
          document.getElementById("pano"),
          {
            position: mylocation, 
            pov: {
              heading: 0,
              pitch: 0,
            },
            visible: true,
          },
        );

          // pano_changed fires whenever the individual pano ID changes. Note that the pano ID (which you can use to reference this panorama) is only stable within the current browser session.
        panorama.addListener("pano_changed", () => {
          const panoCell = document.getElementById("pano-cell");

          panoCell.innerHTML = panorama.getPano();
        });

        // links_changed fires whenever the Street View's links change. Note that this event may fire asynchronously after a change in the pano ID indicated through pano_changed.
        panorama.addListener("links_changed", () => {
          const linksTable = document.getElementById("links_table");

          while (linksTable.hasChildNodes()) {
            linksTable.removeChild(linksTable.lastChild);
          }

          const links = panorama.getLinks();

          for (const i in links) {
            const row = document.createElement("tr");

            linksTable.appendChild(row);

            const labelCell = document.createElement("td");
            labelCell.innerHTML = "<b>Link " + i + "</b>";

            const valueCell = document.createElement("td");
            const headingCell = document.createElement("td");
            
            function isNullOrEmptyExplicit(str) {
              return str === null || str === undefined || str === "";
            }

            description = links[i].description;
            if (isNullOrEmptyExplicit(description) === true) {
              valueCell.innerHTML = "no name";
            } else {
              valueCell.innerHTML = description;
            }

            headingCell.innerHTML = links[i].heading.toFixed(2);

            linksTable.appendChild(labelCell);
            linksTable.appendChild(valueCell);
            linksTable.appendChild(headingCell);
          }
        });
        panorama.addListener("position_changed", () => {
          const positionCell = document.getElementById("position-cell");

          // use .slice(1, -1) to remove the brackets
          positionCell.firstChild.nodeValue = String(panorama.getPosition()).slice(1,-1) + "";
        });
        panorama.addListener("pov_changed", () => {
          const headingCell = document.getElementById("heading-cell");
          const pitchCell = document.getElementById("pitch-cell");

          // use .toFixed(2) to show only 2 decimals
          headingCell.firstChild.nodeValue = panorama.getPov().heading.toFixed(2) + "";
          pitchCell.firstChild.nodeValue = panorama.getPov().pitch.toFixed(2) + "";
        });
      }

      window.initPano = initPano;
    </script>    
  </body>
</html>
