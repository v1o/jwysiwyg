Step 1:
-------
Include the necessary CSS and JS files:
<!-- Include RichText plugin -->
<link rel="stylesheet" href="${contextPath}/javascripts/jwysiwyg/jquery.wysiwyg.css" />
<script type="text/javascript" src="${contextPath}/javascripts/jwysiwyg/jquery.browser.js"></script>
<script type="text/javascript" src="${contextPath}/javascripts/jwysiwyg/jquery.wysiwyg.js"></script>
<script type="text/javascript" src="${contextPath}/javascripts/jwysiwyg/default.js"></script>
<!-- Custom spellchecker plugin for jWYSIWYG -->
<link rel="stylesheet" href="${contextPath}/javascripts/jwysiwyg/plugins/spellchecker/wysiwyg.spellchecker.css" />
<script type="text/javascript" src="${contextPath}/javascripts/jwysiwyg/plugins/spellchecker/wysiwyg.spellchecker.js"></script>


Step 2:
-------
Add a spellcheck control to the toolbar when instantiating your wysiwyg areas:

$.fn.wysiwyg ? $("textarea.richText").wysiwyg({
	controls: {
		spellcheck: {
			visible: true,
			groupIndex: 8,
			callbackArguments: [],
			tooltip: 'Spellcheck',
			exec: function(){
				$(this.editor).wysiwyg("Spellchecker.trigger", this);
			}
		}
	},
}) : null;

Step 3:
-------
Enjoy.