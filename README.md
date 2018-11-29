# PDW File Browser for the TinyMCE and CKEditor WYSIWYG editors.

##Installation

- Copy pdw_file_browser folder to the plugins folder under tiny_mce (/tiny_mce/plugins/)
- See source code for how to add the plugin to your editor setup.

**TinyMCE**
```javascript
$().ready(function() {
  
  $('textarea#example1').tinymce({
    // Location of TinyMCE script
    script_url : "../javascript/tiny_mce/tiny_mce.js",

    // General options
    theme : "advanced",
    skin : "o2k7",
    plugins : "safari, pagebreak, style, layer, table, save, advhr, advimage, advlink, emotions, iespell, inlinepopups, insertdatetime, preview, media, searchreplace, print, contextmenu, paste, directionality, fullscreen, noneditable, visualchars, nonbreaking, xhtmlxtras, template",
    file_browser_callback : "filebrowser",
 
    // Theme options
    theme_advanced_buttons1 : "image, media, link",
    theme_advanced_buttons2 : "",
    theme_advanced_toolbar_location : "top",
    theme_advanced_toolbar_align : "left",
    
    height : '300',
    width : '450'

  });
});

function filebrowser(field_name, url, type, win) {
  
  fileBrowserURL = "/path/to/file/browser/index.php?editor=tinymce&filter=" + type;
    
  tinyMCE.activeEditor.windowManager.open({
      title: "PDW File Browser",
      url: fileBrowserURL,
      width: 950,
      height: 650,
      inline: 0,
      maximizable: 1,
      close_previous: 0
    },{
      window : win,
      input : field_name
    }
  );    
}
```

**CKEditor**
```javascript
<textarea cols="80" id="editor1" name="editor1" rows="10"></textarea>
<script type="text/javascript"> 
//<![CDATA[
 
// This call can be placed at any point after the
// <textarea>, or inside a <head><script> in a
// window.onload event handler.
 
// Replace the <textarea id="editor1"> with an CKEditor
// instance, using default configurations.
CKEDITOR.replace( 'editor1', {
        filebrowserBrowseUrl : '/path/to/pdw_file_browser/index.php?editor=ckeditor',
        filebrowserImageBrowseUrl : '/path/to/pdw_file_browser/index.php?editor=ckeditor&filter=image',
        filebrowserFlashBrowseUrl : '/path/to/pdw_file_browser/index.php?editor=ckeditor&filter=flash',
    }
);
 
//]]>
</script>
```

##Version info

-----------------------------------------
Version 1.4 beta
-----------------------------------------

+ Removed SWF uploader
+ Integrated Flow.js uploader (https://github.com/flowjs/flow.js)

-----------------------------------------
Version 1.3 beta
-----------------------------------------
+ Added Italian language (by Paolo Battistella http://www.paolobattistella.it)
+ Added Serbian language (by krsman http://tinymce.moxiecode.com/punbb/viewtopic.php?pid=81381#p81381)
+ Added Czech language (by Piotr @ SourceForge Project http://sourceforge.net/projects/pdwfilebrowser/)
+ Image preview (A modified version of SlimBox 2 (Christophe Beyls http://www.digitalia.be))
+ Standalone File Browser (Please see http://www.neele.name/filebrowser/standalone.php)
+ Returning links as absolute or relative
+ New skin "Mountain View Dark"
* Rename cookie view to pdw-view because Joomla is using the same cookie

-----------------------------------------
Version 1.2 beta
-----------------------------------------
+ Added Danish language (by Mattias)
+ New Skin "Mountain View"
+ Settings panel to select language and theme/skin
+ Custom filters in addition to Images, Flash and Media
+ Compatible with CKEditor v3 (FCKEditor v2 not tested yet!)
+ Double click to insert files in to the editor
* Upload settings (extensions whitelist, max. upload size) in config.php instead of upload.php
* PHP 5 compatible (serious issues with PHP 5 have been solved)
* Added phpThumb fix for PHP 5.3.x and higher
* Modified actions.php (Error messages are now more clear when creating a folder fails)
* Improved settings for allowing or disallowing actions (including uploading, settings panel and creating folders)
* Added translation function to fall back to English when translation isn't found
* bug fix for creating new folders when open_basedir is active
* First folder in the breadcrumbs at the top is now always upload folder.

-----------------------------------------
Version 1.1.1 beta
-----------------------------------------
+ Added Spanish language (by thedavis http://tinymce.moxiecode.com/punbb/viewtopic.php?pid=79827#p79827)
* Removed var from line 615 in jquery.mediabrowser.js
* Removed var from line 671 in jquery.mediabrowser.js

-----------------------------------------
Version 1.1 beta
-----------------------------------------
+ Added Catalan language (by quisoc http://tinymce.moxiecode.com/punbb/viewtopic.php?pid=79285#p79285)
+ Added French (by tasiot http://tinymce.moxiecode.com/punbb/viewtopic.php?pid=77045#p77045)
+ Added Swedish language (by Swensson http://tinymce.moxiecode.com/punbb/viewtopic.php?pid=75969#p75969)
+ The line "All files (*.*)" in the filter is now also translated
* Solved javascript errors with Internet Explorer (Rename, Cut & Paste, Copy & Paste, Delete are now working)
* Solved various PHP Notice and Strict Standards errors.

-----------------------------------------
Version 1.0 beta
-----------------------------------------
+ Multiple views
+ Flash file uploads
+ Multiple file selections via shift click and ctrl click
+ 30+ file icons
+ Search by filename
+ Filtering
+ Image caching
+ Copy, cut, paste and delete
+ Create new folders
+ Multiple languages support
      + Dutch
      + English
      + German (by redeye86 http://tinymce.moxiecode.com/punbb/viewtopic.php?pid=75021#p75021)
      + Russian (by BonySoft http://tinymce.moxiecode.com/punbb/viewtopic.php?pid=79722#p79722)
+ File information pane
+ Renaming folders and files
+ Skins
      + Redmond (standard)
      + Cupertino
