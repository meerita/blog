---
title: The Utilitarian CSS Methodology
layout: post
category: CSS
summary: We have been programming CSS for a long time wrong. It's time to move forward.
  By using the Utilitarian CSS Methodology, the size of the CSS files is drastically
  reduced and the loading, rendering and painting speed of the websites is significantly
  increased. The projects acquire ease of maintenance and are easier to understand.
subtitle: High performance CSS methodology
---

When I started writing CSS in 1996, I was truly excited: the entire presentation of an HTML document could be defined on a separate sheet and, consequently, every change I wanted to make reverberated everywhere into the presentation of that document. This, as it sounds, was a great deal for us developers. Not having to edit thousands of HTML files by hand, always repeating the same changes, it was something we expected and wanted more than others features that browsers were delivering back then (hello `BLINK` element). But we had a problem: Internet Explorer 3 was the first browser to support the fully CSS 1 standard so the rest of the population were still using Netscape and people didn't switch browsers at all. So we developers had to stick to shitty HTML editing until the majority of people switched or upgraded browsers. That was the reality back then. It is also true that, even if we only had rely on HTML, our biggest pain came from not having awesome content managers nor partials, includes or with Javascript components like we have nowadays. Those who have not yet been taken by the grim reaper should know that long time ago developers used frames to do all this job. It was a very archaic and ugly way to develop, but it was the only thing we had. Today all these things are a kind of urban legend. We no longer have connection speeds issues, lacking of CSS support or compatibility between browsers. Almost everything we mention is quite –but not completely– solved but even with all this awesomeness, we created several other kind of problems.

### We have created a monster

I have always liked to relate the 4 eras of web development, particularly to talk about CSS and to put in context those who still do not understand the monster we have created. The first stage comprises from 1995 to 2001. It was the "Dawn of HTML". Lots of problems derived from this particular time because doing layouts required the abuse of the `TABLE` element like you never imagine. Among other things, we also had the worsts network connection ever; the crazy design styles of that time; the abuse of images –specially transparent GIFs– and other silly Internet trends making loading an entire homepage a sort of a family event. It was very close to an average of 15-20 seconds for each page, even more if you lived overseas.  Yet, in this period of time, we have seen the rise of Flash, in 1997 and Flash 3 by the end of 2000. Even with all those crazy things, CSS wasn't a big thing and only a few daring developers who started to blog about Web Standards used it; most of the projects in the web were done using tables over tables over tables.

When we get into 2001, we started to live the 2nd era of web development, as a call it "The Empire of Flash". It went approximately from 2001 to late 2007 and –with total irruption of the Web Standards on the way– CSS & HTML didn't found its place in developers hearts but more specially, managers, to fight against the Flash empire, a proprietary technology of Macromedia that allowed to create rich websites in animations and interactions. It took 7 years to overthrow the Flash monopoly and it wasn't possible until the iPhone's release to market in 2007 and specially, by the end of 2009: [when Steve Jobs's decided to kill Flash](https://www.apple.com/hotnews/thoughts-on-flash/) that the development standards took off high towards a new direction and no return. 

In 2008 things began to change at a dramatic pace. The irruption of smartphones, tablets and the death of Flash by Apple forced developers and managers to change their strategy. This is what I define as "The Rise of HTML 5". Now developers start using CSS in an intensive and uncontrolled way. Thousands of classes to define everything and if we add the fact that it was necessary to develop methods for several browsers, the size of CSS files began to grow brutally. This great chaos brought calm from the hand of companies such as Yahoo and others, who began to define the first CSS development methodologies, like OOCSS (object oriented CSS) or we can mention ACSS (atomic CSS), BEM (block, element, modifier) or SMACSS (scalable and modular architecture for CSS) among others. These methodologies helped to make the developers work in an orderly fashion, but they did not help reduce the size of the files. On the contrary, many of these methodologies ended up increasing the final size of the files as you can see in this graphic:

<svg class="display--block max-width--75" viewBox="0 0 1024 510" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" style="margin: 0 auto">
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

In the fourth stage of the era of web development, already at the end of 2012, we can say that "The Dominion of Methodologies and Frameworks" begins. An era where almost all developers use either a framework or a methodology. Here we can see two patterns: the first one, because the developers when using frameworks not only increase the size of the CSS file by default (they use all the components by default) but they add more code on top to overwrite the default styles that the frameworks offer at first. This can be seen without problems in many of the analyzed sites, where they use entire libraries for a few necessary styles. In the second case, the use of methodologies, the developers commit the sin of atomizing each component until it becomes useless, creating more and more components as the project grows. No matter how thought the architecture is, it shows that it does not work over time, creating more redundant code. It is not a matter of incompetence of the developer: it is the methodology that encourages the creation of components, modifiers and more modifiers to cover all unthinkable cases. This era is characterized by making the developer have tools to develop more comfortably, but not more effective.

### The importance of the file size

In order to understand the impact of CSS, we need to take a good example of projects that lasted since 1995 –most of them died after couple years or after a decade–, to achieve this, **I have found newspapers to be the perfect example group**  for this research. When I got the first data of the research, I saw the trend was very clear: each year –with some highs and lows, though– the size increased significantly and in a very similar pattern for each of the group subjects, but after a year of activity, **the trend keep up every single year**, including on 2019.

I already know exactly the reasons why that happened: First, the developers moved all the logic of building the UI to CSS hoping their CSS components will cover all needs to their websites but, over the time, they started to stack up more and more code, therefore, as the business and activity of these projects grew, so the CSS file did it. Second,  developers –having no longer the Browser's War in their tables– began to use both new methodologies (such as BEM or OOCSS) and frameworks (such as YUI, Bootstrap, Foundation, etc.) by increasing the base code of each project, partly because the methodologies are very verbose like all the constraints that frameworks bring to the scene, making developers go to technical debt unconsciously and with ease. Third, because there was an explosion of libraries that offered functionalities, such as the YUI or JQuery libraries, which allowed developers to easily include calendars and other components. These libraries inflated CSS size as I could check on more than one occasion.

By the end of 2018, we continue to see the same pattern of problems. But at this point, what I see is mostly the collateral effect of overturning all the responsibility of building the CSS architectures. As a fact, developers have spared no effort in reducing the code but rather in expanding it, ending with a kind of testament of all the structures that can not be changed due to the amount of necessary refactor on every new design and thus repeating thousands of times the same properties and values, as I can see, in the most read newspaper of all Spain, MARCA:


<table class="border--1 border-style--solid border-collapse--collapse text-align--center" style="margin: 0 auto">
  <caption class="font-weight--bold padding--8">Times a  property appears in the same CSS file</caption>
  <thead>
    <tr>
      <th class="padding--8 border--0 border-bottom-width--1 border-right-width--1 border-style--solid">display</th>
      <th class="padding--8 border--0 border-bottom-width--1 border-right-width--1 border-style--solid">color</th>
      <th class="padding--8 border--0 border-bottom-width--1 border-right-width--1 border-style--solid">height</th>
      <th class="padding--8 border--0 border-bottom-width--1 border-right-width--1 border-style--solid">font-size</th>
      <th class="padding--8 border--0 border-bottom-width--1 border-right-width--1 border-style--solid">display</th>
      <th class="padding--8 border--0 border-bottom-width--1 border-right-width--1 border-style--solid">padding</th>
      <th class="padding--8 border--0 border-bottom-width--1 border-right-width--1 border-style--solid">margin</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="padding--8 border-right-width--1 border-right-style--solid">2029</td>
      <td class="padding--8 border-right-width--1 border-right-style--solid">1464</td>
      <td class="padding--8 border-right-width--1 border-right-style--solid">1416</td>
      <td class="padding--8 border-right-width--1 border-right-style--solid">1308</td>
      <td class="padding--8 border-right-width--1 border-right-style--solid">1249</td>
      <td class="padding--8 border-right-width--1 border-right-style--solid">942</td>
      <td class="padding--8">902</td>
    </tr>
  </tbody>
</table>

In the previous table we can smell fire: the unnecessary repetition of classes and properties, increasing significantly the CSS file. With the Internet connection speeds we have today, it may be a minor problem, but that problem does not lie in the transfer itself (which is, partly) but in the amount of code that has to be created and maintained, as well, reuse all those classes in future cases. Most of the projects analyzed fell into these dilemmas: use what has been done or create more classes to avoid conflicts. In general, what I see is developers creating more and more CSS architecture and having a clear technical debt problem by thinking their architecture truly solves their problems: if you want to modify MARCA's website, you need to really refactor +9000 lines of code of CSS, meaning that you also have to through each component in their CMS platform and apply new redesigned classes, fixes and the list goes on.

That's why these projects would never be fully redesigned and refactored properly: the amount of stones in the backpack is too damn much, so the responsibility to take care of it. That's why over these years I've been thinking how this problem can be solved, and I have found it under the wonderful Utilitarian CSS Methodology.

### Utilitarian CSS methodology

> Designed to be useful rather than decorative.

The Utilitarian CSS Methodology, from now on, "UCSS", is a new approach I established to solve the problem of programming, scaling and maintaining CSS projects. It bases everything with the creation of **single class attribute utilities** rather than collection of classes than define entire components with some base styles. Each of these CSS properties represents an unique CSS property and its possibles values, like `font-weight--bold` or `display--block`. Every single CSS property can be built in our main CSS file, but instead of doing that, we just generate the needed properties and values for our projects, maintaining an strict weight on our CSS files. How the code would look like? Here's an easy example:

If we have a flash alert component defined like this:

<pre class="white-space--pre-wrap">
&lt;div class="overlay overlay--flash-alerts"&gt;
  &lt;div class="flash flash--main"&gt;
    &lt;p class="flash__title flash__title--small flash__title--error"&gt;Phone number is invalid&lt;/p&gt;
    &lt;p class="flash__text flash__text--small flash__text--error"&gt;Phone numbers must be 9 digits, without spaces&lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre>

In UCSS this JS component would be:

<pre class="white-space--pre-wrap">
&lt;div class="display--flex flex-direction--column-reverse justify-content--flex-end position--fixed top--0 bottom--0 left--0 right--0 z-index--10"&gt;
  &lt;div class="background--000 color---f00"&gt;
    &lt;h3 class="margin--0 font-size--14"&gt;Phone number is invalid&lt;/h3&gt;
    &lt;p class="margin--0 font-size--12"&gt;Phone numbers must be 9 digits, without spaces&lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre>

Or either this minified UCSS:

<pre>
&lt;div class="d--f f-d--c-r j-c--f-e p--f t--0 b--0 l--0 r--0 z-i--10"&gt;
  &lt;div class="b--000 c---f00"&gt;
    &lt;h3 class="m--0 f-s--14"&gt;Phone number is invalid&lt;/h3&gt;
    &lt;p class="m--0 f-s--12"&gt;Phone numbers must be 9 digits, without spaces&lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;
</pre>

If we analyze both examples, we can see that in the first example, all the classes are descriptive, but relative to their form, not their content in CSS properties. We do not know for sure what `overlay` or `flash__title` does. We can guess something, but we are not quite sure. We also don't know if any of the classes present there is overwritten by another rule. We have little information.

In this first example we already imagine the problems that will come once the project goes forward in development. The use of classes to describe components causes us to end up forgetting the very nature of each one. Soon, we will start creating new classes to do the same things that we had already defined at the beginning. This is a common pattern in web development. It happens a lot: creating a class `nav` with its initial modifiers (like `--principal`, `--aside` or `--categories`) but as the project grows, we realize that not all modifiers can do the job and we end up creating different types of `nav` classes using synonyms (like `buttons`, `options`, etc.) because, it does not make sense to overwrite 100% of the navigation rules to create a new thing from scratch. To do so, it supposes not only to create more instructions, also it supposes to keep to the problems of inheritance, therefore, we ended up creating new classes from scratch again, to get a cleaner code, with the right instructions to create other structures of navigation.

In the second example, **we have a clear understanding what is going on:** everything is separated and explicit in purpose, meaning that, we can change anything in the JS module without having to edit 1 single line of our CSS file and we will have our changes instantly done. We also know all the behavior and that we don't have any constraint to remove things or overwritten rules to watch for, no inheritance problems. That is utilitarianism at its best: in the first example, it has to share properties with other structures defined in the CSS, grossing the CSS file over the time and increasing technical debt. In the second, the CSS file is not engrossed, we just re-use all the properties in our JS module, when needed.

Then our next question is, why would you do that instead of using inline-css? My answer is simple: inline CSS is good, but it has its caveats:

* You will have serious problems to do responsive.
* You will miss all the power of selectors and pseudo selectors.
* You will start using !important if you want to use an external CSS file.
* You will have troubles to read properties once you have more than 3 o 4. 
* You cannot pre and post process it.
* It's not comfortable to modify it with JS or other languages due it's strict nature. 
* You will also have troubles to apply vendor prefixes.
* You may end with CSS inline and CSS in files, messing your architecture by a lot.

UCSS means you can have both of the best worlds: inline power to apply whatever rule you need and the flexibility of classes. For example:

<pre class="white-space--pre-wrap">
&lt;div class="sm-display--none md-display--grid c-warning"&gt;
  &lt;h3&gt;This is a warning&lt;/h3&gt;
  &lt;p class="color--2"&gt;Your profile needs to be updated.&lt;/p&gt;
&lt;/div&gt;
</pre>

In this example, we see that our `sm-display--none` only works for mobile, while `md-display-grid` will overwrite the previous class when we are using a bigger screen. We also spot something new: `c-warning`, and we know that `c-` belongs to "custom" class. This class is used to trigger stuff we cannot do as if we were programming with pure UCSS, every time you see a custom class, you know it's man-made, therefore, a change in behavior or property is happening outside the JS world. In this case, for example, `c-warning` in our `custom.scss` does this:

<pre class="white-space--pre-wrap">
.c-warning:hover {
  background: map-get($colors, 1);
}
</pre>

So now we can see that our custom class it's there because we need to specify behavior, in this case `:hover`, and that's all. Your custom class will be stored in one file, where you can quickly get to it and modified it. There's no constraints what you can do with.

This approach give you all these benefits:

* Extreme performance (more below)
* You can define the needed values for each property in CSS.
* You will not fear breaking other things in your project.
* Say goodbye to `!important`
* You will not have class names conflicts over the years.
* You will use only the properties that you need, always. You don't need to repeat color: #f00 200 times in your CSS.
* You don't need to extend your architecture, just build it right away in the JS module.
* You don't need to perform maintenance as if you were maintaining several KBs of CSS.
* You will use less code, way less code.
* Excellent legacy support: you don't need to refactor your JS module and your CSS file, because you're using the same CSS over and over again. You just need to focus on changing the modules. That's all.

Utilities in CSS aren’t a new thing. You may be creating some for your projects. You may be using some for a long time if you were using Bootstrap or other custom made frameworks at your company, but you didn’t fully used utilities in this particular way to convey an entire philosophy and architectural design as I designed it for UCSS. That’s why UCSS is quite new, even that you may encounter some projects that have more or less utilities, these rely on their own naming conventions and none of these translate CSS as accurate and strictly as UCSS. Having said that, the ultimate goal of UCSS is to allow developers to concentrate the logic in the real components that bring logic and data (JS or your favorite language) rather than creating those things in a set of .css files. UCSS is compatible with anything you used, even if you want to use it partially, it will be always the minimum CSS needed. It is also compatible with your components, like forms or buttons.

### Performance

As a general rule, any hit to the server delays the compilation of the website. Since HTML is the first doc served and processed by the browser, inline CSS (or styles in the `HEAD`) will be faster in performance that serving external CSS files. But sometimes this is not possible or it doesn't scale as we want so we use external CSS file with caching rules. Without having this properly done, the page will be either white for a couple of seconds while the browser waits the CSS to be processed into a CSSOM. So, the faster this file is delivered to the browser, the faster will be the page rendered. UCSS will be always trumping over conventional CSS development: the files are really tiny that, in most cases, you will be putting it into the `HEAD` instead of serving it through external CSS files. Even taking the external option will result in faster delivery of CSS to the browser. Most of the files created with the UCSS framework (more below) do not surpass the 15KB of file size compressed. 

Another frequently ignored point is resource loading into the browser, which means how much time the browser takes to understand the HTML, JS, CSS and other resources you provided. This time spent by the browser usually is milliseconds but sometimes it could grow up above the second, this means that the browser will be stuck for that time blocking the rendering and painting jobs. As a fact, any CSS file that is big in selectors and properties will load slower. Due the nature of BEM and other methodologies, file sizes ends with an incredible amount of rules, so much as over 9.000 rules or even higher numbers, as I've mentioned above. This adds an extra time loading the CSS and processing it to render the CSS tree. When I started this project, I've made several tests loading different types of CSS files and their equivalent to UCSS in order to test the loading performance and the results were pretty shocking. The MARCA analysis, as an example, gave me an average loading speed of 84,7ms (only for the CSS file) while the UCSS equivalent averaged 6,7ms.

The last and most important point to mention in this performance section is rendering time. Once the browser has built the CSSOM –in the loading job–, the rendering instructions begins its job to deliver the painting process. Lots of things can affect the rendering time: JS code and webfonts (specially), CSS effects (like `box-shadow`, filters, background images, fonts, etc.) amount of resources to load, slow selectors and pseudo selectors, etc. UCSS outperforms any other methodology: it is so explicit that render times are greatly improved. In all tests with different projects in complexity, I've got performance gains from an average of 175ms to a mere 17ms. That's insanely fast. This is given because of the explicit nature of the single class CSS and the lack of all the rules in play at that moment. In a test in the lab, we have found that even un-styled pages aren't that faster than the same HTML styled with UCSS due the nature of the CSS provided on the default browser's CSS stylesheets. So amazing as that.

### The framework

UCSS [has a framework](https://github.com/meerita/utilcss) of my own. It is written in SCSS, so it can be practically adopted in any project, even on those with PostCSS. The major differences of this framework are:

* Configurable Normalizer.
* Configurable set of properties.
* Configurable variables: colors, scales, properties.
* CSS 1, 2 and 3 support of most of the properties.

One of the dilemmas that has always bothered me is the use of [normalizer](https://necolas.github.io/normalize.css/). Everyone installs normalizer, but few comment on the sections they will never use, therefore, each project already dedicates 6 KB to styles that will never be used. The UCSS framework [has a normalizer module](https://github.com/meerita/utilcss/blob/master/modules/normalizer.scss), which complies with all normalizer rules, but these are activated according to what you need. To start using it, you need to go to the [config_normalizer.scss file](https://github.com/meerita/utilcss/blob/master/modules/config_normalizer.scss) and start changing the variables to `true` so that it automatically takes effect. No more cost of KBs without impact on the site. You can have your customizer, as I recommend as a philosophy to have the best CSS code: only the classes that are needed.

The most important part of the framework [is the property configuration file](https://github.com/meerita/utilcss/blob/master/modules/config_css.scss). In order to have the perfect CSS –or the closest thing to this concept– you have to configure the properties file so that it only builds the necessary properties. The default framework has all the properties configured as `false`. That means that, throughout your development, if you want for example to have the possibility of having a class that brings the color, you must first go to the file of `config_css.scss` and look in the configuration for the line` config-color`. In this way, the preprocessor in the next construction will build the class `.color -` that you need, with the color that you specify in the `vars.scss` file, of course. In this way, you will always have strict control of what is produced and not what is not. If you stop using the color property, then you can go to the configuration file and turn the property to `false`. The idea of UCSS is that **you always have the necessary classes, no more, no less**. As an example, this website, was built 100% entirely with UCSS framework and the final size compressed is 1.142 bytes. That is almost nothing, nothing as 4 KBs of code that I directly put in the `HEAD` of the each document. No delays. We go from 55ms processing to 5ms.

Once we know which CSS property we want to use, for example: `display`, `word-break`, etc. now we only need to finish configuring the values that we will need for each of these properties. To do this, we need to open the `_vars.scss` file where we will find the Sass maps with the possible values for each CSS property. For example, for `display` we will see:

<pre class="white-space--pre-wrap">
$displays: (
  // none,
  block,
  // inline,
  // inline-block,
  // flex,
  grid
  );
</pre>

In the variable file, we will find the map `displays` with these values. In this example, `displays` has the values `none`,` inline`, `inline-block`,` flex` commented and has `block`, `grid` enabled. If we uncomment any of the `display` property in the configuration file, the framework will process everything and generate these classes:

<pre class="white-space--pre-wrap">
.display--block {
  display: block
}

.display--grid {
  display: grid
}
</pre>

If we want to enable `flex`, you simply need to remove the comment from the `//flex` line, and the Sass generator will compile it in the next build. It's that simple: in the variable file you can also create your own values, both for the colors and for the scales of `padding` and `margin` among other properties. It is a convenient way to activate and deactivate property values and have total control of them.

This framework doesn't output nice forms, or headers or hero sections. You have to build them using the set of classes on your own. This is freedom. You will never have to overwrite dozens of lines of preset CSS to achieve your design, in fact, you will be astonish how tiny the CSS will become and how easy to mantain your project will be.

### Were we are now

Creating this methodology requires data, a lot of data to be sure of its effectiveness. In the last 6 months, I have created code with UCSS both in projects for clients and as examples to measure the performance between the real example and my example of UCSS. I would like developers to use UCSS in their projects so that this project continues to grow and become more solid over time. The more examples we have of UCSS, the more we can understand the possible problems that it may have (although I do not find too many). If you have a project that is using UCSS, let me know.