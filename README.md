# email-signature

Simple email signature block in plain-Jane html, with a little shadow fakery using tables.

If you like it, feel free to use and abuse. If you hate it, that's cool too 🙂

**Update**
The first signature isn't email safe. It relies on border radius and other techniques that I'm now
discovering email clients don't support (wtf).

Preview signature 1 [here](https://bigupjeff.github.io/email-signature/email-signature.html)

Preview signature 2 [here](https://bigupjeff.github.io/email-signature/email-signature-new.html)

## Signature 1
This signature isn't email safe. It relies on border radius and other techniques that I'm now
discovering email clients don't support (wtf). Only use it if you think your recipients use
respectable email clients such as Thunderbird, or you just don't care.

Besides not being email-safe, it demonstrates a cool shading technique using nested tables!

## Signature 2
I've tried to implement some email compliancy hacks mainly based on the advice at
htmlemailcheck.com. Notable issues are listed below:

#### .ExternalClass CSS fix for Outlook.com
By default, Outlook.com centers your email by placing it inside a div with a class named
`ExternalClass` using the styles `display:inline-block; line-height: 131%`. These have no effect when
using IE, however in every other browser, the email will not be centered. *See
[here](https://www.htmlemailcheck.com/knowledge-base/recommended-externalclass-css-fix-outlook-com/)
for the fix details.*

#### <style> element not supported in Yandex Mail
The `<style></style>` tag (CSS selectors, classes, and ids) is not supported in Yandex Mail. Try
placing important styles which affect the emails layouting and design as inline styles. *As many of
the styles that can be inlined, have been inlined. The only content in the `<style>` being fixes for
Outlook and a link hover style which isn't essential.*

#### Yahoo! Mail Android only supports styles within the body
For an unknown reason, the Yahoo! Mail Android app only supports the style tag (`<style></style>`)
when it's placed within `<body></body>`. *Sorry Yahoo users, I draw the line at ridiculous HTML
doc structure.*

#### !important styles
Any inline styles using the !important declaration will be ignored in Outlook 2007. *Styles have
been preceded with a property and value withouth the !important flag. Fingers crossed.*

Yahoo! Mail removes the !important rule if there is a space between the display declaration and
!important. *All important rules have been written without a space as is acceptable as per CSS
standards - just crappy to read.*

#### width styles
The width style is supported across most email clients, with only partial support on table elements
in Outlook 2007 to Outlook 2016 and Windows 10 Mail. *What can you do?*

#### max-width style
The max-width style is not supported in 13 known email clients, with only partial support (not
supported on tables) in Android 4.4.4 Mail, BlackBerry and should be avoided from implementing.
*What can you do?*

#### border-radius styles
The border-radius style is not supported in 12 known email clients and should be avoided from
implementing. *The radius styles in this signature are only to give the window a softer appearance
and are not essential to the design.*

#### Gmail .ii a[href] class override
Gmail strips most inline styles and applies it's own rules in flagrant disregard for your code.
Using the `.ii a[href] {` class stops gmail from colouring visited links.

#### Gmail handling inline styles diffrently on different elements
I haven't delved into this too far, but let's say I used 3 x `<b>`s in a row - Gmail will clear
the rules from the `<style>` attribute on the centre one. If I wrap the text in a `<span>` and apply
the `<style>` attribute to that inside the centre `<b>`, they remain intact.

#### Table-wrapper responsive hack
`max-width` isn't supported in emails. To get around that, I've use a hack that involves wrapping
the content in another table and placing the content inside a `<td>` with the desired max width set
as the HTML `width` attribute. The second empty `<td>` pushes the content cell to the left. When
the window is less than the width of the first `<td>`, the cell will respond.

E.g: `<table width="100%"><tr><td width="500px">[content here]</td><td></td></tr></table>`

## Check email-safe CSS properties and HTML elements
https://www.caniemail.com/


## Linting for email HTML
https://www.htmlemailcheck.com/check/

Test your email HTML in as many email client and platforms as you can!