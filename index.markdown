---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<html>
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
      body, html {
        height: 100%;
        margin: 0;

      }

      .hero-image {
        background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url({{site.baseurl}}/images/BannerImage.jpeg);
        height: 50%;
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
        position: relative;
      }

      .hero-text {
        text-align: center;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        color: white;
      }

      .hero-text button {
        border: none;
        outline: 0;
        display: inline-block;
        padding: 10px 25px;
        color: black;
        background-color: #ddd;
        text-align: center;
        cursor: pointer;
        border-radius: 12px;
      }

      .hero-text button:hover {
        background-color: #555;
        color: white;
      }
      .sourcing-text{
        text-align: right;
        color: white;
      }
    </style>
  </head>
  <body>

    <div class="hero-image">
      <div class="hero-text">
        <h1 style="font-size:50px">CISTERN</h1>
        <p>A Database of Geographical Knowledge in the Ottoman World</p>
        <button onclick="location.href='{{site.baseurl}}/about/';">ABOUT</button>
      </div>
      <div class="sourcing-text">
        <h3 style="font-size:10px">Source: Library of Congress</h3>
      </div>
    </div>


<!-- <p>Page Content..</p> -->

  </body>
</html>
