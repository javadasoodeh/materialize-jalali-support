
<p align="center">
  <a href="http://materializecss.com/">
    <img src="http://materializecss.com/res/materialize.svg" width="150">
  </a>
</p>

<h3 align="center">MaterializeCSS with Jalali Datepicker Support</h3>

<p align="center">
  Materialize, a CSS Framework based on material design, now with Jalali datepicker support.
  <br>
  <a href="http://materializecss.com/"><strong>-- Browse the docs --</strong></a>
  <br>
  <br>
  <a href="https://travis-ci.com/Dogfalo/materialize">
    <img src="https://travis-ci.com/Dogfalo/materialize.svg?branch=master" alt="Travis CI badge">
  </a>
  <a href="https://badge.fury.io/js/materialize-css">
    <img src="https://badge.fury.io/js/materialize-css.svg" alt="npm version badge">
  </a>
  <a href="https://cdnjs.com/libraries/materialize">
    <img src="https://img.shields.io/cdnjs/v/materialize.svg" alt="CDNJS version badge">
  </a>
  <a href="https://david-dm.org/Dogfalo/materialize">
    <img src="https://david-dm.org/Dogfalo/materialize/status.svg" alt="dependencies Status badge">
    </a>
  <a href="https://david-dm.org/Dogfalo/materialize#info=devDependencies">
    <img src="https://david-dm.org/Dogfalo/materialize/dev-status.svg" alt="devDependency Status badge">
  </a>
  <a href="https://gitter.im/Dogfalo/materialize">
    <img src="https://badges.gitter.im/Join%20Chat.svg" alt="Gitter badge">
  </a>
</p>

## Table of Contents
- [Quickstart](#quickstart)
- [Documentation](#documentation)
- [Supported Browsers](#supported-browsers)
- [Changelog](#changelog)
- [Testing](#testing)
- [Contributing](#contributing)
- [Changes for Jalali Datepicker Support](#jalali-datepicker)
- [Copyright and license](#copyright-and-license)

## Quickstart:
Read the [getting started guide](http://materializecss.com/getting-started.html) for more information on how to use materialize.

- [Download the latest release](https://github.com/Dogfalo/materialize/releases/latest) of materialize directly from GitHub. ([Beta](https://github.com/Dogfalo/materialize/releases/))
- Clone the repo: `git clone https://github.com/Dogfalo/materialize.git` (Beta: `git clone -b v1-dev https://github.com/Dogfalo/materialize.git`)
- Include the files via [cdnjs](https://cdnjs.com/libraries/materialize). More [here](http://materializecss.com/getting-started.html). ([Beta](https://cdnjs.com/libraries/materialize/1.0.0-beta))
- Install with [npm](https://www.npmjs.com): `npm install materialize-css` (Beta: `npm install materialize-css@next`)
- Install with [Bower](https://bower.io): `bower install materialize` ([DEPRECATED](https://bower.io/blog/2017/how-to-migrate-away-from-bower/))
- Install with [Atmosphere](https://atmospherejs.com): `meteor add materialize:materialize` (Beta: `meteor add materialize:materialize@=1.0.0-beta`)

## Documentation
The documentation can be found at <http://materializecss.com>. To run the documentation locally on your machine, you need [Node.js](https://nodejs.org/en/) installed on your computer.

### Running documentation locally
Run these commands to set up the documentation:

```bash
git clone https://github.com/Dogfalo/materialize
cd materialize
npm install
```

Then run `grunt monitor` to compile the documentation. When it finishes, open a new browser window and navigate to `localhost:8000`. We use [BrowserSync](https://www.browsersync.io/) to display the documentation.

### Documentation for previous releases
Previous releases and their documentation are available for [download](https://github.com/Dogfalo/materialize/releases).

## Supported Browsers:
Materialize is compatible with:

- Chrome 35+
- Firefox 31+
- Safari 9+
- Opera
- Edge
- IE 11+

## Changelog
For changelogs, check out [the Releases section of materialize](https://github.com/Dogfalo/materialize/releases) or the [CHANGELOG.md](CHANGELOG.md).

## Testing
We use Jasmine as our testing framework and we're trying to write a robust test suite for our components. If you want to help, [here's a starting guide on how to write tests in Jasmine](CONTRIBUTING.md#jasmine-testing-guide).

## Contributing
Check out the [CONTRIBUTING document](CONTRIBUTING.md) in the root of the repository to learn how you can contribute. You can also browse the [help-wanted](https://github.com/Dogfalo/materialize/labels/help-wanted) tag in our issue tracker to find things to do.

## Changes for Jalali Datepicker Support

This fork of MaterializeCSS includes added support for the Jalali (Persian) calendar in the datepicker component. 

### How to Use:
- Include the `jalaali.min.js` script before MaterializeCSS:
  
```html
<script src="path/to/jalaali.min.js"></script>
```

- Initialize the datepicker with the `calendarType` set to `'jalali'`:

```javascript
M.Datepicker.init(elems, {
    calendarType: 'jalali', // Switch between Jalali or Gregorian
    format: 'yyyy-mm-dd',  // Jalali date format
    i18n: {
        cancel: "لغو",
        clear: "پاک کردن",
        done: "تأیید",
        previousMonth: "‹",
        nextMonth: "›",
        months: ["فروردین", "اردیبهشت", "خرداد", "تیر", "مرداد", "شهریور",
            "مهر", "آبان", "آذر", "دی", "بهمن", "اسفند"],
        weekdays: ["یکشنبه", "دوشنبه", "سه‌شنبه", "چهارشنبه",
            "پنجشنبه", "جمعه", "شنبه"],
    }
});
```

### Example:
Here’s a basic example of how to use the Jalali datepicker:

```html
<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <title>Persian Datepicker with Materialize CSS</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/css/materialize.min.css">
</head>
<body>
    <input type="text" class="datepicker" id="datepicker">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/jalaali-js@1.2.7/dist/jalaali.min.js"></script>
    <script src="dist/js/materialize.min.js"></script>
    <script type="text/javascript">
        document.addEventListener('DOMContentLoaded', function () {
            const elems = document.querySelectorAll('.datepicker');
            M.Datepicker.init(elems, {
                calendarType: 'jalali',
                format: 'yyyy-mm-dd',
                i18n: {
                    cancel: "لغو",
                    clear: "پاک کردن",
                    done: "تأیید"
                },
                onDraw: function (instance) {
                    // Find the footer specific to the modal of this datepicker instance
                    const modalFooter = instance.modalEl.querySelector('.datepicker-footer');
                    // Add the "Go to Today" button if it doesn't exist
                    let todayButton = instance.modalEl.querySelector('.datepicker-today-button');
                    if (!todayButton) {
                        todayButton = document.createElement('button');
                        todayButton.setAttribute("data-id", instance.el.getAttribute("id"))
                        todayButton.className = 'datepicker-today-button btn-flat green-text text-darken-2';
                        todayButton.textContent = 'برو به امروز';  // "Go to Today" in Persian
                        todayButton.style.width = '50%';
                        
                        modalFooter.appendChild(todayButton)

                        todayButton.addEventListener('click', function () {
                            const datepickerElems = document.querySelector(`#${this.getAttribute("data-id")}`);
                            const instance = M.Datepicker.getInstance(datepickerElems);
                            const todayDate = new Date();
                            instance.setDate(todayDate);
                            instance.gotoDate(todayDate);  // Navigate to today's date
                        });
                    }
                }
            });
        });
    </script>
</body>
</html>
```

### Output
<p align="center">
  <a href="#">
    <img src="https://github.com/javadasoodeh/materialize-jalali-support/blob/v1-dev/images/jalali-output.png" width="500">
  </a>
</p>

## Copyright and license
Code Copyright 2018 Materialize. Code released under the MIT license.
