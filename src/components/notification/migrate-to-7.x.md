### HTML

All notification variations have been condensed into two files `inline-notification.html` and `toast-notification.html`.

There are now two data attributes for `notification.js` to target. `[data-notification]` identifies the component and `[data-notification-btn]` marks the button to close a notification.

The majority of the class names have changed along with some structural changes. The class name changes are documented below. However, probably the easiest way to migrate to the 7.0 component is just by copy/pasting in the new HTML.

### SCSS

The `_notification.scss` file is now located at __src/components/notification/notification.scss__. You will need to update any `@import` statements for this file to reflect this change.

```scss
@import 'path_to_node_modules/@console/bluemix-components/src/components/notification/notification';
```
Quite a few class names have changed. See table below.

| Old Class                      | New Class: Inline                     | New Class: Toast                     |
|--------------------------------|---------------------------------------|--------------------------------------|
| bx--notification__title        | bx--inline-notification__title        | bx--toast-notification__title        |
| bx--notification__subtitle     | bx--inline-notification__subtitle     | bx--toast-notification__subtitle     |
| bx--notification__caption      | N/A                                   | bx--toast-notification__caption      |
| bx--notification__close-button | bx--inline-notification__close-button | bx--toast-notification__close-button |
| bx--notification__icon         | bx--inline-notification__icon         | bx--toast-notification__icon         |

To specify the type of notification you'll add a modifier class.

`<div class="bx--toast-notification bx--toast-notification--success">`

Previously this was all handled by one class.

`<div class="bx--notification-inline--warning">`

Here are the possible modifiers.

| bx--inline-notification          | bx--toast-notification          |
|----------------------------------|---------------------------------|
| bx--inline-notification--error   | bx--toast-notification--error   |
| bx--inline-notification--success | bx--toast-notification--success |
| bx--inline-notification--info    | bx--toast-notification--info    |
| bx--inline-notification--warning | bx--toast-notification--warning |

### JavaScript

New in 7.0 we now have JavaScript to handle closing a notification! As long as you have the data attributes discussed in the HTML section and the JavaScript is initialized it'll just work. For more details see the component README file.
