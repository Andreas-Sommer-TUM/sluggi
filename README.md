# sluggi — The little TYPO3 CMS slug helper

## What does it do?

The extension … 
* modifies the page slug field, so normal users can only edit the part of the page slug they have appropriate permissions on the related pages (see screenshot and example below)
* allows administrators to restrict editing the page slug on certain pages
* renames slug segments recursively, so if you change the slug of a parent page, the segments of this page are updated in all slugs on child pages. [Redirects](https://docs.typo3.org/typo3cms/extensions/core/Changelog/9.1/Feature-83631-SystemExtensionRedirectsHasBeenAdded.html) are created for all _old_ paths too.
* sets a fallback chain for page slug calculation as follows (the first nonempty value is used): Alternative page title > Page title (you can change the fields used in the extension configuration)
* configures a replacement of forward slashes (`/`) in the page slug with a hyphen (`-`) for new pages (existing pages are not affected as long as you don't recalculate the slugs)

# Extension settings

You can configure all options for the extension via Admin Tools > Settings > Extension Configuration

![sluggi Settings](Resources/Public/Screenshots/sluggi_options.png)

# Backend editor example

![sluggi Features](Resources/Public/Screenshots/sluggi_features.png)

In this example the editor has no rights to edit the _About_ page of the website, so he has no permission to change the _/about/_ segment of the URL too.

You can set a whitelist with backend user group IDs in the extension configuration. Members of these groups will still be able to edit the whole slug.

## Requirements

You need at least TYPO3 CMS version 9.5.5 including the following features:

* https://docs.typo3.org/typo3cms/extensions/core/Changelog/9.5.x/Feature-86740-AllowRemovalOfSlashInSlug.html
* https://docs.typo3.org/typo3cms/extensions/core/Changelog/9.5.x/Feature-87085-FallbackOptionsForSlugFields.html

## Installation

Require the package:

    composer require wazum/sluggi

Available on packagist:
https://packagist.org/packages/wazum/sluggi

## Required core patch

You have to apply the patch from https://review.typo3.org/c/Packages/TYPO3.CMS/+/60263
before TYPO3 CMS 9.5.6 or 10.0.1

## Support me

You like my extensions? Get something for me (surprise! surprise!) from my wishlist on [Amazon](https://smile.amazon.de/hz/wishlist/ls/307SIOOD654GF/) or [help me pay](https://www.paypal.me/wazum) the next pizza or Pho soup (mjam). Thanks a lot!