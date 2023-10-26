# Zero setup banner for websites to show support for Palestine

Use this snippet to show your support for Palestine on the top of your website. Installing it takes minutes.

1. [About](#about)
2. [Installation](#installation)
3. [Reporting issues](#reporting-issues)

## About

This code adds a small black banner on top of your website with Palestine flag and support message. It links to Aman Palestine donation site but you can change the link to point to a support channel of your choice.

Even though the banner has been tested on multiple websites it has some issues for example on sites with sticky navigation.

![Example of the banner](support-banner-screenshot.png "Example of the banner")

## Installation

Installation is dead simple. Just copy this code to your template right before the closing `<body>` tag.

```
<script>
// Support Palestine Banner by eWallz
function createBanner() {
  // Create the banner container
  var banner = document.createElement('a');
  banner.className = 'support-palestine';
  banner.href = 'https://jommenyumbang.com/ms/home';// set your link here
  banner.target = '_blank'; // Open the link in a new tab

  // set your text here
  var bannerContent = `
    <div class="support-palestine-flag" role="img" aria-label="Flag of Palestine">
      <svg xmlns="http://www.w3.org/2000/svg" width="40" height="20" viewBox="0 0 1000 500">
        <path fill="#000000" d="M 0.5,-0.5 C 333.5,-0.5 666.5,-0.5 999.5,-0.5C 999.5,55.1667 999.5,110.833 999.5,166.5C 740.43,166.832 481.43,166.499 222.5,165.5C 147.785,111.14 73.7851,55.8071 0.5,-0.5 Z"/>
        <path fill="#e3312b" d="M -0.5,-0.5 C -0.166667,-0.5 0.166667,-0.5 0.5,-0.5C 73.7851,55.8071 147.785,111.14 222.5,165.5C 223.475,167.193 224.808,168.693 226.5,170C 261.897,196.026 296.897,222.526 331.5,249.5C 295.481,277.191 259.481,304.857 223.5,332.5C 148.63,387.437 74.2969,443.103 0.5,499.5C 0.166667,499.5 -0.166667,499.5 -0.5,499.5C -0.5,332.833 -0.5,166.167 -0.5,-0.5 Z"/>
        <path fill="#fefefe" d="M 222.5,165.5 C 481.43,166.499 740.43,166.832 999.5,166.5C 999.5,221.833 999.5,277.167 999.5,332.5C 740.833,332.5 482.167,332.5 223.5,332.5C 259.481,304.857 295.481,277.191 331.5,249.5C 296.897,222.526 261.897,196.026 226.5,170C 224.808,168.693 223.475,167.193 222.5,165.5 Z"/>
        <path fill="#268024" d="M 223.5,332.5 C 482.167,332.5 740.833,332.5 999.5,332.5C 999.5,388.167 999.5,443.833 999.5,499.5C 666.5,499.5 333.5,499.5 0.5,499.5C 74.2969,443.103 148.63,387.437 223.5,332.5 Z"/>
      </svg>
    </div>
    <div class="support-palestine__label" style="color: white; margin-left: 10px; text-align: center;">
      Donate to support Palestine Freedom ❤️
      <span class="mobile-hidden">#Solidarity4Palestine #Pray4Palestine</span>
    </div>
  `;

  banner.innerHTML = bannerContent;

  // edit your color & styles here
  banner.style.position = 'fixed';
  banner.style.left = '0';
  banner.style.top = '0';
  banner.style.right = '0';
  banner.style.background = 'linear-gradient(rgb(28 178 226), rgb(80 134 238))'; // Gradient background
  banner.style.display = 'flex';
  banner.style.justifyContent = 'center';
  banner.style.paddingTop = '5px';
  banner.style.paddingBottom = '5px';
  banner.style.zIndex = '9999'; // Ensure the banner is above the header
  banner.style.textDecoration = 'none';
  banner.style.fontFamily = 'Arial';

  // Append the banner to the body
  document.body.appendChild(banner);

  // add element id - class to be shifted below banner (with !important to force it)
  var contentBelowBanner = document.querySelector('.navbar');
  if (contentBelowBanner) {
    contentBelowBanner.style.marginTop = '60px !important'; // Adjust the margin value as needed
  }

  // second text will be hidden on mobile
  var style = document.createElement('style');
  style.innerHTML = `
    @media (max-width: 768px) {
      .mobile-hidden {
        display: none;
      }
    }
  `;
  document.head.appendChild(style);
}

window.addEventListener('load', createBanner);
</script>
```
**Another tuned floating version:**
```
<div id="widget-stand-for"></div>
<script position="top-right">
!function(){const n=document.currentScript.getAttribute("position"),t=(Date.now(),document.createElement("div"));function e(n){"function"==typeof gtag?gtag("event",n,{event_category:"Widget",event_label:"Widget Interaction"}):"function"==typeof ga&&ga("send","event","Widget","Widget Interaction",n)}t.id="widget-stand-for",t.style.display="none",document.body.appendChild(t),window.addEventListener("load",(function(){!function(n,t="top-left"){const o=document.getElementById(n),i="widget-stand-for",d=document.createElement("div");o.appendChild(d);const a=document.createElement("div");let s;switch(t){case"top-left":s="position: fixed; top: 100px; right: 0; z-index: 9999;";break;case"top-right":s="position: fixed; top: 100px; right: 0; z-index: 9999;";break;case"bottom-left":s="position: fixed; bottom: 0; left: 0; z-index: 9999;";break;case"bottom-right":s="position: fixed; bottom: 0; right: 0; z-index: 9999;";break;default:s="position: fixed; top: 120px; right: 0; z-index: 9999;"}a.style.cssText=s,a.classList.add(`${i}-container`);const r=document.createElement("div");r.id="logoDiv";let c="auto";"top-left"===t?c="auto auto auto 0":"top-right"===t?c="auto 0 auto auto":"bottom-left"===t?c="0 auto auto 0":"bottom-right"===t&&(c="0 0 auto auto");r.innerHTML=`<div style="display: inline-block; margin:10px; width:100px;"><img src="https://lh3.googleusercontent.com/-qvogSiDXv1A/VhE2QlT970I/AAAAAAAAkHU/voORgrp3zyU/s1600/palestine-flag-animation.gif" /></div>`,r.addEventListener("click",f);const l=document.createElement("div");l.id="contentDiv",l.classList.add("d-none"),l.innerHTML='<div class="custom-card"><div class="custom-card-header"><a href="javascript:;" class="custom-card-close-button" id="closeButton" aria-label="Close">X</a></div><div class="custom-card-body"><img class="custom-card-image" src="https://peaceforpalestine.cc/wp-content/uploads/2023/10/palestine.png" alt="Support Palestine"><h1 class="custom-card-title">Support Palestine</h1><p class="custom-card-text">Join us in showing solidarity with Palestine</p><span class="custom-card-badge">#WeStandWithPalestine</span><a href="https://peaceforpalestine.cc" target="_blank" class="custom-card-link" id="learnMore">Get This Badge</a></div></div>';const p="@import url('https://fonts.googleapis.com/css2?family=Inter:wght@200;300;400;600&family=Nunito:wght@200;300;400;700&family=Roboto:wght@300;500&display:swap');#widget-stand-for #logoDiv svg {width: 100px;height: auto;cursor: pointer; margin: 20px;}#widget-stand-for .card {margin: 10px;padding: 10px;text-align: center;max-width: 100%;}#widget-stand-for .card-title {font-size: 18px;}#widget-stand-for .wsf-link {color: #fff !important;}#widget-stand-for .custom-card {border: 1px solid #e0e0e0;box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);border-radius: 5px;width: 300px;margin: 20px;font-family: 'Inter', 'Nunito', 'Roboto', sans-serif;text-align: center;background: #fff;font-size:14px;}#widget-stand-for .custom-card-header {display: flex;justify-content: flex-end;padding: 10px;}#widget-stand-for .custom-card-close-button {background: none;border: none;font-size: 20px;cursor: pointer;}#widget-stand-for .custom-card-body {padding: 20px;}#widget-stand-for .custom-card-image {width: 100%;max-width: 100%;margin-bottom: 20px;display: block;}#widget-stand-for .custom-card-title {font-size: 24px;font-weight: bold;margin: 0; animation: wave 2s infinite;}@keyframes wave {0% { transform: rotate(0deg); } 50% { transform: rotate(5deg); } 100% { transform: rotate(0deg); }}#widget-stand-for .custom-card-text {font-size: 16px;margin: 20px 0;}#widget-stand-for .custom-card-badge {background-color: #28a745;color: #fff;padding: 5px 10px;border-radius: 5px;margin-bottom: 20px;display: inline-block;}#widget-stand-for .custom-card-link {display: block;background-color: #343a40;color: #fff;padding: 10px;text-align: center;text-decoration: none;border-radius: 5px;margin-top: 10px;font-weight: bold;}#widget-stand-for .custom-card-link:hover {background-color: #000;color: #fff;}#widget-stand-for .d-none { display: none; }#widget-stand-for .custom-card-close-button {background: #333;border: none;color: white;font-size: 14px;cursor: pointer;position: absolute;top: 10px;right: 10px;z-index: 1;border-radius: 50%;width: 30px;height: 30px;display: flex;justify-content: center;align-items: center;}#widget-stand-for .custom-card-close-button:hover {background: #000;}",g=document.createElement("style");g.innerHTML=p,o.appendChild(g),a.appendChild(r),a.appendChild(l),o.appendChild(a);function f(){l.classList.contains("d-none")?(l.classList.remove("d-none"),r.classList.add("d-none"),e("Widget Opened")):(l.classList.add("d-none"),r.classList.remove("d-none"),e("Widget Closed"))}l.querySelector("#closeButton").addEventListener("click",f),o.style.display="block"}("widget-stand-for",n)}))}();
</script>
```
Credits to: https://peaceforpalestine.cc

## Installation via Google Tag Manager

You can also easily install the banner with GTM.

1. Log into Tag Manager
1. Go to Tags view
1. Click New to add new tag
1. Set tag type to Custom HTML
1. Paste the snippet above to HTML field
1. Add All Pages trigger
1. Publish your changes



## Reporting issues

We are open for any feedback. Use GitHub [issue tracker](https://github.com/ewallz/stand-for-palestine/issues) to report issues.
