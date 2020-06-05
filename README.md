HTML export template with a Table Of Contents for Zim Desktop Wiki
=============================================================

## Description
Template to export your [Zim wiki](http://www.zim-wiki.org/) notebook as a website with mobile theme. See the [Zim manual](http://zim-wiki.org/manual/Help/Export.html) for more information on exporting your notebook. 

The template uses jquery and jquerymobile to create responsive webpages with an index and a table of contents in a side panel. It is a mobile-first design which however also looks good on your desktop. The template offers some pointers in the sourcecode to customize the design to fit the users need.  

## Version
This template works with Zim 0.67 and maybe also with 0.61.

This template is based on the [ecodiv-mobile](https://github.com/ecodiv/ZIM-templates/tree/master/Ecodiv-mobile) template by Paulo van Breugel for Zim 0.61.

Compared to the original template, this one brings the following changes:
* a dynamic table of contents based on the headers in the document's content, thanks to [tocbot](https://tscanlin.github.io/tocbot/).
* updated jquery and jquery-mobile libraries.
* improved CSS with more natural margins and justified text.
* compatibility with static site hosters, such as GitHub Pages, such as linking libraries with https instead of http.
* default title is "Notebook" instead of "My website title".

Note: if you want to host on GitHub Pages (the only way currently to avoid CORS issues), the `_resources` folder must be placed at the root of your github pages branch, and rename it to `resources` without a leading underscore, else [GitHub Pages will ignore it per Jekyll standards](https://help.github.com/en/github/working-with-github-pages/about-github-pages-and-jekyll).

## Example
An example of this template hosted on GitHub Pages is available here:
* https://lrq3000.github.io/non24article/SleepNon24.html

## Adapting the template for your own use
The template can be used as it is, but most likely you will want to make some changes. If you open the ecodiv_mobile_withtoc.html file, you will see a few comments (text between <!--  -->) with suggestions for changes to consider.

## Installing the template

1. Download the files 
2. Copy or move the `ecodiv_mobile_withtoc.html` and `ecodiv_mobile_withtoc` folder from there to the ~/.local/share/zim/templates/html on Linux, else on Windows open Zim Notes, click on Edit > Templates, then click on the Browse button at the bottom. This will create a new folder and open it in a window of the Windows Explorer. In this folder, create a subfolder `html`, then inside place the content of this github repository.

### Note
* You do not need to move the ecodiv.html and ecodiv folder to the ~/.local/share/zim/templates/html folder. It is convenient as it makes the template available through the drop down menu (File --> Export) and it is available through Edit --> Template. However, when exporting you can always select a template from any location on your computer. So, if you copy the ecodiv.html and ecodiv folder to e.g., your Documents folder, you can then select the ecodiv.html from there using File --> Export menu.

* But whatever solution you go for, just make sure to copy the folder ecodiv to the same folder as the ecodiv.html file, otherwise the result will not be as intended.

### Issues
When you run the website from your computer in Chrome and click on a link, you may see the message "cannot load page". You can however open the link in a new tab using the context menu (right click). This is only a problem when running the website from your computer (i.e., when using the file:/// protocol). It will run without problem from your webserver (i.e., when using the http:// protocol).

The problem is that Chrome does not seem to handle Ajax based links used in JqueryMobile when running from the local computer. This is mainly a problem when you want to test or further develop your website from your computer using Chrome. 
This issue maybe solved in future releases of jquerymobile, but for now the easiest solution is to use Firefox instead. And if you have few links only, you can remedy this by adding rel="external" as an attribute into the link anchor tag. For example:

```<a href="./Home/Test_1.html" title="+Test 1" class="page" rel="external">```

This needs to be done manually after creating the website in Zim, so not really a solution if you have many pages and many links.

If you really want to use Chrome for local testing / developing your website, you can perhaps force Chrome in accepting local file links. I am not even sure if that is possible, but see e.g., https://forum.jquery.com/topic/chrome-do-not-handle-ajax-based-jquery-mobile-single-page-navigation-model.

If you have suggestions or tips to solve this issue, please leave your comments here: https://github.com/ecodiv/Ecodiv-mobile/issues/2

## Authors

* Paulo van Breugel (github: [ecodiv](https://github.com/ecodiv)), 2017-2018.
* Stephen Larroque (github: [LRQ3000](https://github.com/lrq3000)), 2020.

## License

GNU General Public License v3+
