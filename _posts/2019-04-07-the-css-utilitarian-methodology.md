---
title: The CSS Utilitarian Methodology
layout: post
date: '2019-04-27 19:14:36'
category: CSS
summary: We have been programming CSS for a long time wrong. It's time to move forward.
  By using the CSS Utilitarian Methodology, the size of the CSS files is drastically
  reduced and the loading, rendering and painting speed of the websites is significantly
  increased. The projects acquire ease of maintenance and are easier to understand.
subtitle: High performance methodology
---

When I started programming in CSS in 1996, I was excited: the entire presentation of an HTML document could be defined on a separate sheet and, consequently, every change I wanted to make reverberated everywhere. Internet Explorer 3 was the first browser to support the fully CSS 1 standard. This, as it sounds, was a great deal for us developers. Not having to edit thousands of HTML files by hand, always repeating the same changes, was something we expected and wanted more than others features that browsers were delivering back then. This has happened because, basically, before there were no content managers, nor partials, includes or with Javascript components as we have today. Those who have not yet been taken by the grim reaper, long time ago people used frames to do all this work. It was a very archaic and ugly way to develop. But it was the only thing we had. This, in 1995, meant a huge glory for developers, since all the development fell on the abuse of HTML hacks and its attributes taking hours and hours to change a simple document or, to create it from scratch. Yes, we used nested `TABLE` elements, transparent and animated GIFs, Java applets, popups, text as images and more, but never anything like CSS. Today all these things are a kind of urban legend. We no longer have the problem of connection speed, nor of frameworks or, of compatibility between browsers. Today almost everything we mention is almost solved but even that, we created several other kind of problems.

### We created a monster

I have always liked to relate the 4 eras of web development, particularly to talk about CSS and to place in context those who still do not understand the monster we have created. The first stage comprises from 1995 to 2001. It was the "Dawn of HTML". Lots of problems derived from this particular time because doing layouts required the abuse of the `TABLE` element like you never image, among other things, we had the worsts network connection, the crazy design styles of that time, the abuse of images –specially transparent GIFs– and other silly internet trends making loading an entire homepage were a family event, very close to an average of 15-20 seconds for each page, even more if you lived overseas.  Yet, in this lapse of time, we have seen the rise of Flash, in 1997 and Flash 3 by the end of 2000. Even with all those crazy things, CSS wasn't a big thing and only a few daring developers who started to blog about Web Standards used it; most of the projects in the web were done using tables over tables over tables.

When we got in 2001, with total irruption of the Web Standards, CSS did not find its place where to become powerful against Flash, a proprietary technology of Macromedia that allowed to create rich sites in animations and interactions. It took 6 years to overthrow the Flash monopoly on the Internet, and it was not until the iPhone's exit in 2007 and Steve Jobs's decision to kill Flash that the development standards took off high towards a new direction and no return . Since then, despite having replaced the HTML tables with the DIVs and other more appropriate elements, both the HTML documents and the CSS **files did not stop growing in size** as shown in this graphic that is part of a study what am I doing:

<svg class="max-width--100" viewBox="0 0 1024 510" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <!-- Generator: Sketch 53.2 (72643) - https://sketchapp.com -->
    <title>average css file size</title>
    <desc>Created with Sketch.</desc>
    <g id="average-css-file-size" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
        <rect fill="#FFFFFF" x="0" y="0" width="1024" height="510"></rect>
        <text id="Title" font-family="SFProDisplay-Regular, SF Pro Display" font-size="24" font-weight="normal" letter-spacing="-0.217500001" fill="#222222">
            <tspan x="264.537734" y="42"  class="font-family--sans">Average CSS file size (KB) for Spanish newspapers</tspan>
        </text>
        <g id="Group" transform="translate(44.000000, 84.000000)">
            <path d="M8.125,341.25 C8.125,341.25 21.4583333,341.25 48.125,341.25 L88.125,341.25 L128.125,341.25 L168.125,341.25 L208.125,338.75 L248.125,337.5 L288.125,338.75 L328.125,335 L368.125,333.75 L408.125,325 L448.125,312.5 L488.125,278.75 L528.125,263.75 L568.125,185 L608.125,173.75 L648.125,90 L688.125,6.25 L728.125,13.75 L768.125,106.25 L808.125,123.75 L848.125,83.75 L888.125,123.75 L928.125,107.5" id="Path" stroke="#03A1FF" stroke-width="3.75"></path>
            <circle id="Dot" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="8.125" cy="341.25" r="5"></circle>
            <circle id="Dot-2" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="48.125" cy="341.25" r="5"></circle>
            <circle id="Dot-2-Copy" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="88.125" cy="341.25" r="5"></circle>
            <circle id="Dot-2-Copy-2" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="128.125" cy="341.25" r="5"></circle>
            <circle id="Dot-2-Copy-3" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="168.125" cy="341.25" r="5"></circle>
            <circle id="Dot-2-Copy-4" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="208.125" cy="338.75" r="5"></circle>
            <circle id="Dot-2-Copy-5" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="248.125" cy="337.5" r="5"></circle>
            <circle id="Dot-2-Copy-6" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="288.125" cy="338.75" r="5"></circle>
            <circle id="Dot-2-Copy-7" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="328.125" cy="335" r="5"></circle>
            <circle id="Dot-2-Copy-8" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="368.125" cy="333.75" r="5"></circle>
            <circle id="Dot-2-Copy-9" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="408.125" cy="325" r="5"></circle>
            <circle id="Dot-2-Copy-10" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="448.125" cy="312.5" r="5"></circle>
            <circle id="Dot-2-Copy-11" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="488.125" cy="278.75" r="5"></circle>
            <circle id="Dot-2-Copy-12" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="528.125" cy="263.75" r="5"></circle>
            <circle id="Dot-2-Copy-13" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="568.125" cy="185" r="5"></circle>
            <circle id="Dot-2-Copy-14" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="608.125" cy="173.75" r="5"></circle>
            <circle id="Dot-2-Copy-15" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="648.125" cy="90" r="5"></circle>
            <circle id="Dot-2-Copy-16" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="688.125" cy="6.25" r="5"></circle>
            <circle id="Dot-2-Copy-17" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="728.125" cy="13.75" r="5"></circle>
            <circle id="Dot-2-Copy-18" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="768.125" cy="106.25" r="5"></circle>
            <circle id="Dot-2-Copy-19" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="808.125" cy="123.75" r="5"></circle>
            <circle id="Dot-2-Copy-20" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="848.125" cy="83.75" r="5"></circle>
            <circle id="Dot-2-Copy-21" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="888.125" cy="123.75" r="5"></circle>
            <circle id="Dot-2-Copy-22" stroke="#03A1FF" stroke-width="2.5" fill="#FFFFFF" cx="928.125" cy="107.5" r="5"></circle>
            <text id="1996" transform="translate(8.125000, 369.750000) rotate(-90.000000) translate(-8.125000, -369.750000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="-5.58349612" y="374.25">1996</tspan>
            </text>
            <text id="1997" transform="translate(48.125000, 369.000000) rotate(-90.000000) translate(-48.125000, -369.000000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="34.9052734" y="373.5">1997</tspan>
            </text>
            <text id="1998" transform="translate(88.125000, 369.750000) rotate(-90.000000) translate(-88.125000, -369.750000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="74.4287109" y="374.25">1998</tspan>
            </text>
            <text id="1999" transform="translate(128.125000, 369.750000) rotate(-90.000000) translate(-128.125000, -369.750000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="114.428711" y="374.25">1999</tspan>
            </text>
            <text id="2000" transform="translate(168.125000, 370.000000) rotate(-90.000000) translate(-168.125000, -370.000000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="153.713623" y="374.5">2000</tspan>
            </text>
            <text id="2001" transform="translate(208.125000, 369.500000) rotate(-90.000000) translate(-208.125000, -369.500000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="194.630127" y="374">2001</tspan>
            </text>
            <text id="2002" transform="translate(248.125000, 369.500000) rotate(-90.000000) translate(-248.125000, -369.500000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="233.817871" y="374">2002</tspan>
            </text>
            <text id="2003" transform="translate(288.125000, 369.500000) rotate(-90.000000) translate(-288.125000, -369.500000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="273.683594" y="374">2003</tspan>
            </text>
            <text id="2004" transform="translate(328.125000, 370.000000) rotate(-90.000000) translate(-328.125000, -370.000000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="313.982178" y="374.5">2004</tspan>
            </text>
            <text id="2005" transform="translate(368.125000, 370.000000) rotate(-90.000000) translate(-368.125000, -370.000000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="354.018799" y="374.5">2005</tspan>
            </text>
            <text id="2006" transform="translate(408.125000, 370.000000) rotate(-90.000000) translate(-408.125000, -370.000000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="393.835693" y="374.5">2006</tspan>
            </text>
            <text id="2007" transform="translate(448.125000, 370.250000) rotate(-90.000000) translate(-448.125000, -370.250000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="434.324463" y="374.75">2007</tspan>
            </text>
            <text id="2008" transform="translate(488.125000, 370.000000) rotate(-90.000000) translate(-488.125000, -370.000000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="473.8479" y="374.5">2008</tspan>
            </text>
            <text id="2009" transform="translate(528.125000, 370.000000) rotate(-90.000000) translate(-528.125000, -370.000000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="513.8479" y="374.5">2009</tspan>
            </text>
            <text id="2010" transform="translate(568.125000, 369.500000) rotate(-90.000000) translate(-568.125000, -369.500000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="554.630127" y="374">2010</tspan>
            </text>
            <text id="2011" transform="translate(608.125000, 368.250000) rotate(-90.000000) translate(-608.125000, -368.250000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="595.546631" y="372.75">2011</tspan>
            </text>
            <text id="2012" transform="translate(648.125000, 369.000000) rotate(-90.000000) translate(-648.125000, -369.000000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="634.734375" y="373.5">2012</tspan>
            </text>
            <text id="2013" transform="translate(688.125000, 369.500000) rotate(-90.000000) translate(-688.125000, -369.500000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="675.100098" y="374">2013</tspan>
            </text>
            <text id="2014" transform="translate(728.125000, 369.500000) rotate(-90.000000) translate(-728.125000, -369.500000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="714.898682" y="374">2014</tspan>
            </text>
            <text id="2015" transform="translate(768.125000, 369.500000) rotate(-90.000000) translate(-768.125000, -369.500000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="754.935303" y="374">2015</tspan>
            </text>
            <text id="2016" transform="translate(808.125000, 369.500000) rotate(-90.000000) translate(-808.125000, -369.500000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="794.752197" y="374">2016</tspan>
            </text>
            <text id="2017" transform="translate(848.125000, 369.000000) rotate(-90.000000) translate(-848.125000, -369.000000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="835.045654" y="373.5">2017</tspan>
            </text>
            <text id="2018" transform="translate(888.125000, 369.500000) rotate(-90.000000) translate(-888.125000, -369.500000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="874.764404" y="374">2018</tspan>
            </text>
            <text id="2019" transform="translate(928.125000, 369.500000) rotate(-90.000000) translate(-928.125000, -369.500000) " class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
                <tspan x="914.764404" y="374">2019</tspan>
            </text>
        </g>
        <text id="0" class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
            <tspan x="30.4960937" y="429">0</tspan>
        </text>
        <text id="100" class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
            <tspan x="17.4047851" y="313">100</tspan>
        </text>
        <text id="200" class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
            <tspan x="16.0925293" y="196">200</tspan>
        </text>
        <text id="300" class="font-family--sans" font-size="12.5" font-weight="normal" letter-spacing="-0.113281244" fill="#222222">
            <tspan x="15.9582519" y="80">300</tspan>
        </text>
    </g>
</svg>

If we take Spanish newspapers as a reference, the trend is clear: each year the size increased. And we know exactly the reasons why that happened. That happened because during 2007 to the present, developers have been experimenting with different methodologies and frameworks that have only become redundant, slow to maintain and impossible to scale. Another proof of this is the performance tests we have carried out, and we can clarify that among the 5 most important newspapers, the repetition of attributes is immense and unnecessary:

[gráfico atributos]

In the previous graphic we can already smell fire: the unnecessary repetition of classes and properties, increasing significatively the CSS file. With the internet connection speeds we have today, it may be the minor problem, but that problem does not lie in the transfer (which is) but in the amount of code that has to be maintained, as well, reuse all those classes. Most of the projects analyzed fell into these dilemmas: use what has been done or create more classes to avoid conflicts.