# Intructions for updating tinymce to a newer version:

1. Change ways in lms/envs/common.py and cms/envs/common.py
2. Edit init of tinymce
3. Replace old tinymce to a new in common/static/js/vendor/tinymce
    ```
	  install new tinymce:
          nuget install TinyMCE
	  add old jquery.tinymce.min.js to common/static/js/vendor/tinymce/js/tinymce
	  add codemirror in tinymce/plugins from https://github.com/openedx/edx-platform/tree/open-release/olive.2/common/static/js/vendor/tinymce/js/tinymce/plugins
	  replace tinymce directories
    ```
4. Change ways in configs
5. Generate a bundled version of the TinyMCE with all the plugins using the following command
    ```
    cd common/static/js/vendor/tinymce/js/tinymce
    LC_ALL=C cat tinymce.min.js */*/*.min.js plugins/emoticons/js/emojis.min.js > tinymce.full.min.js
    ```

