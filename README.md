<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="initial-scale=1, maximum-scale=1, user-scalable=no">
  <title>ArcGIS API for JavaScript Tutorials: Display a Web Map</title>
  <style>
    html, body, #viewDiv {
      padding: 0;
      margin: 0;
      height: 100%;
      width: 100%;
    }
  </style>
  <link rel="stylesheet" href="https://js.arcgis.com/4.18/esri/themes/light/main.css">
  <script src="https://js.arcgis.com/4.18/"></script>

  <script>
    require([
      "esri/config",
      "esri/Map",
      "esri/WebMap",
      "esri/views/MapView",
      "esri/widgets/ScaleBar",
      "esri/widgets/Legend"
    ], function(esriConfig, WebMap, MapView, ScaleBar, Legend) {

    esriConfig.apiKey = "YOUR-API-KEY";

      const webmap = new WebMap({
        portalItem: {
          id: "432a3318b69842a6a32bfeb6c628c5ef#"
        }
      });

      const view = new MapView({
        container: "viewDiv",

        map: webmap

      });

      const scalebar = new ScaleBar({
        view: view
      });

      view.ui.add(scalebar, "bottom-left");

    const legend = new Legend ({
        view: view
      });
      view.ui.add(legend, "top-right");

  });
  </script>
</head>
<body>
  <div id="viewDiv"></div>
</body>
</html>


