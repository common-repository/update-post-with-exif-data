=== Update Post with EXIF data (UNMAINTAINED) ===
Contributors: markhowellsmead
Donate link: https://www.paypal.me/mhmli
Tags: exif, iptc, geo, geoencoding, location, tags, taxonomy, post_meta
Requires at least: 4.3
Tested up to: 4.6.1
Stable tag: 1.3.1.1
License: GPL v3 or later
License URI: http://www.gnu.org/licenses/gpl-3.0.html

THIS PLUGIN IS NO LONGER MAINTAINED. Reads in EXIF data of Post Thumbnail, then adds Post tags and a custom meta value containing the serialized GPS location data of the Post's Featured Image.

== Description ==

THIS PLUGIN IS NO LONGER MAINTAINED.

If the appropriate checkboxes are selected in the Post submit box when saving the Post, the plugin reads the EXIF data of the Post's <em>Featured Image</em> and adds Post Tags and a custom meta value “<em>location</em>” containing the serialized GPS location data of the image.

* If the Post has no Featured Image, or if the Featured Image's EXIF data is incomplete, then nothing happens.
* The EXIF data is read directly from the image file, not from a database entry.
* If standard values “GPSLongitude” and “GPSLatitude” are not available in the Featured Image's EXIF data, the post will not be updated with the custom meta field. (A pre-existing value will not be deleted, if this happens.)
* When saving Post Tags, the standard taxonomy <code>post_tag</code> is set. If you need to modify this, for example in the case of a custom taxonomy, then you can use the filter hook <code>update-post-with-exif-data/post_taxonomy</code> to change it.
* If you want to see the custom meta value containing serialized GPS location data in the WordPress backend, you'll need to parse the data and add this field yourself. A good solution for this is the “Advanced Custom Fields” plugin by Elliot Condon, with field type “Google Map”.
* Developers: see the code for a WordPress action hook <code>update-post-with-exif-data/no-gps</code>, which fires in the event that there is no valid GPS data available in the Featured Image.


== Installation ==

1. Upload the plugin folder to the `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress

== Changelog ==

= 1.3.1.1 =
* Correct version number in README.

= 1.3.1 =
* Additional safeguards in the event of missing GPS data in the EXIF array.
* Add <code>update-post-with-exif-data/no-gps</code> action hook to function <code>addImageLocationToPost</code>.

= 1.3.0 =
* <strong>Breaking change</strong>: filter hook <code>post_exif_data_taxonomy</code> is now renamed <code>update-post-with-exif-data/post_taxonomy</code>.
* <strong>Bugfix</strong>: check to ensure that both GPSLongitude and GPSLatitude are set before updating location meta.
* Add unique PHP namespace.
* Comply with PSR-2 coding standards.
* Add action to assist with debugging.
* Extend plugin description for better clarification.

= 1.2.2 =
* Confirmation of compatibility with WordPress 4.6.

= 1.2.1.1 =
* Fix typo in README.

= 1.2.1 =
* Confirmation of compatibility with WordPress 4.5.

= 1.2.0 =
* Replace hard-coded list of customized taxonomy keys with standard taxonomy `post_tag`, and add filter to allow this
to be customized by third parties.
* Clean up code (whitespace, commenting).

= 1.1.1 =
* Corrections to version numbering in README/SVN.
* Confirmation of support in WordPress 4.4.2.
* No functional changes.

= 1.1 =
* Initial public version.
