---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style type="text/css">
      body, html {
        width: 100%;
        height: 100%;
        margin: 0;

      .container-vid{
        position: relative;
        margin: 0 auto;
        width: 100%;
        height: 100%;
      }
      #vid{
        position: fixed;
        right: 0;
        bottom: 0;
        height: auto  !important;
        width: 100%   !important;
        object-fit: scale-down;
        overflow: hidden;
      }
      #button{
        background: rgba(0, 0, 0, 0.5);
        color: #f1f1f1;
        width: 100%;
        padding: 20px;
      }
    </style>
  </head>
  <body>
    <div style="position: relative; margin: 0 auto; width: 100%; height: 100%  !important; display: inline-block;">
      <video id="vid" playsinline autoplay muted style="position: fixed; width: 100%  !important; height: 50%; object-fit: cover;" onended="endVideo()">
        <source src="{{site.baseurl}}/images/WebsiteBanner2.mp4" type="video/mp4">Browser does not support HTML5 video
      </video>

      <button id="but" disabled onclick="location.href='{{site.baseurl}}/about/';" style="position: absolute; top: 65%; left: 50%; transform: translate(-50%, -50%); -webkit-transform: translate(-50%, -50%); visibility: hidden; border: none; outline: 0; display: inline-block; padding: 10px 25px; color: black;
      background-color: #ddd; font-family: BlinkMacSystemFont; text-align: center; cursor: pointer; border-radius: 12px;">LEARN MORE</button>
    </div>
    <script>
      var button = document.getElementById("but");
      var vid = document.getElementById("vid");

      function endVideo(){
        if (vid.ended){
          button.disabled = false;
          button.style.visibility = "visible";
          vid.style.filter= "brightness(0.55)";
        }
      }

    </script>

  </body>
