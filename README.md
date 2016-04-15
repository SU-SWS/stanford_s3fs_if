#[Stanford S3FS Insert Filter](https://github.com/SU-SWS/stanford_s3fs_if)
##### Version: 7.x-1.0

Maintainers: [jbickar](https://github.com/jbickar), [sherakama](https://github.com/sherakama), [boznik](https://github.com/boznik)

[Changelog.txt](CHANGELOG.txt)

This module provides a text filter to force image derivatives in WYSIWYG fields to go through the `_s3fs_image_style_deliver()` function (provided by the [S3FS Drupal module](https://drupal.org/project/s3fs)). It converts direct links to static image derivatives on Amazon Web Services' (AWS) Simple Storage Service (S3) into site-relative links, e.g.,

from:
`<img src=https://my-s3-bucket-name.s3-us-west-2.amazonaws.com/s3fs-public/styles/large/public/filename.jpg?itok=gqtfpDVm" ...`

into:
`<img src="/s3/files/styles/large/public/filename.jpg?itok=gqtfpDVm" ...`

The reason for doing this is to get around a conflict between the [Insert](https://drupal.org/project/insert) module and the [S3FS ](https://drupal.org/project/s3fs) module, whereby Insert will use the direct path to an image derivative on S3 in a WYSIWYG field if the asset exists. If that asset later disappears for some reason (e.g., `drush image-flush --all`), broken image links in WYSIWYG fields result.

See [this issue](https://www.drupal.org/node/2663674) and [this issue in the s3fs module's issue queue](https://www.drupal.org/node/2339067) for more information.

Caveats
---

This module potentially could have severe performance impacts on your site.

This module potentially could have unintended consequences.

This module is in an extremely early developmental state, and probably should not be used by anyone.


Installation
---

Install this module like any other module. [See Drupal Documentation](https://drupal.org/documentation/install/modules-themes/modules-7)

Configuration
---

Nothing special needed.

Troubleshooting
---

If you are experiencing issues with this module try clearing your caches. Twice. If you are still experiencing issues try posting an issue on the GitHub issues page.

Contribution / Collaboration
---

You are welcome to contribute functionality, bug fixes, or documentation to this module. If you would like to suggest a fix or new functionality you may add a new issue to the GitHub issue queue or you may fork this repository and submit a pull request. For more help please see [GitHub's article on fork, branch, and pull requests](https://help.github.com/articles/using-pull-requests)
