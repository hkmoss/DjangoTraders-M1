# DjangoTraders Project Log

## September 6, 2026

### CSS Changes

Customer icon:
- HTML class: `dt-icon`
- Original color: `var(--dt-steel)`
- New color: `var(--dt-gold)`

Product icon:
- HTML class: `dt-icon-supplier`
- Original color: `var(--dt-sage)`
- New color: `darkorange`

### What I Learned

- How to inspect an icon using Chrome DevTools
- How to find CSS classes in VS Code using Ctrl+F
- Difference between CSS variables and color names
- How to hard refresh Chrome with Ctrl+Shift+R

##  September 8    changed the Customers table header from Bootstrap's dark gray to your DjangoTraders customer-theme steel blue.
thead.table-dark th {
  background-color:

  ## 2026-09-07: Added City Search to Customer List

### Goal
Add a City search field to the Customer List page using the same search pattern already implemented for Company Name, Contact Name, and Country.

### Changes Made

#### 1. customer_list.html
Added a new City search input field to the existing search form.

```html
<input type="text"
       name="city"
       class="form-control"
       placeholder="City"
       value="{{ search_city }}">