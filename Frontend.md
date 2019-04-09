### Browser Support
We currently only test EvaP with the latest version of Firefox and Chrome.
This allows the use of modern features, even if it breaks some older browsers.

### Size Support
Only a small set of pages is designed for smaller screen sizes.


Page            | `xs` | `sm` | `md` | `lg` | `xl`
----------------|------|------|------|------|------
General         |  no  |  no  |  no  |  no  | yes
`student/vote`  |  no  |  no  |  yes |  yes | yes

### Framework
We use Bootstrap as a frontend-framework.
Using Bootstrap's components or utilities is preferred over custom styles.
Contrary to other third-party vendors, Bootstrap is included as a Git submodule.
Other libraries are simply checked into our source.

### Stylesheets
Our styles are found as `.scss` files in `static/scss`.
The modularization is kept at a small level:

- `evap.scss` is the main entry point and contains mostly imports and general styles for the page.
- `_variables.scss` and `_colors.scss` define Bootstrap variables and some custom colors.
- `components/` organizes smaller files, each representing a component.
    The components are the same like in Bootstrap.
    Adjustments to Bootstrap classes will be found in the matching component.
    Also, we have some custom components, like `_distribution-bar`.
- `_utilities.scss` contains classes which only overwrite a single property. They can be compared with Bootstrap's utilities.
- `_adjustments.scss` fixes some Bootstrap bugs and modifies smaller third-party vendors.

### JavaScript
Third-party JavaScript lives in `static/js`.
Most of our custom JavaScript is backed into the templates.
Bigger portions of JavaScript code is contained in an own template file.
