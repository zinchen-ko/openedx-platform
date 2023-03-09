# Instructions for updating tinymce to a newer version:

Example of updating: https://github.com/openedx/edx-platform/commit/51b5e624b31dbca8615a8855813ac3c1bfa23872#diff-c78548ba0296575da7a0efc133523a50d78adf17af53f890b0efd2a771b006a2

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
