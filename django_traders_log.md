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

       9/8/2026

Completed Contact Title search functionality on the Customer List page.

Changes made:

- Added contact_titles queryset to customer_list view in views.py.
- Added search_contact_title = request.GET.get("contact_title", "").
- Added contact_titles and search_contact_title to the context dictionary.
- Updated Customer.search() in models.py to accept a contact_title parameter.
- Added contact_title filtering to the Customer.search() method.
- Added a Contact Title dropdown to customer_list.html using the Country dropdown as a template.
- Verified dropdown values populate correctly from the database.
- Verified selecting a Contact Title filters the customer list correctly.
- Added a Contact Title column to the Customer List table.
- Added customer.contact_title to the table row display.
- Tested and verified all search functionality is working.

Additional accomplishments:

- Installed Git.
- Configured Git username and email.
- Initialized DjangoTraders as a local Git repository.
- Created and configured a .gitignore file.
- Created initial Git commit.
- Created GitHub repository: DjangoTraders-M1.
- Connected local repository to GitHub.
- Successfully pushed project to GitHub and established origin/main tracking.

Result:
Customer List page now supports searching by Contact Title and displays Contact Title in the customer table. Project is now under Git version control and backed up to GitHub.

9/9/2026

Completed Requirement 4 UI/UX improvements.

Changes made:

- Added a Low Stock badge to Product List when units_in_stock is below 10.
- Used Bootstrap badge styling and a Font Awesome warning icon.
- Added an empty search-results alert when no products match search criteria.
- Reworked the empty-state implementation to avoid a DataTables warning by displaying the alert outside the table.
- Added a Category column to the Product List results table.
- Verified Category values display correctly for all products.
- Verified Supplier and Category searches continue to function correctly.
- Tested all changes and confirmed no DataTables warnings remain.

Result:
Product List now provides clearer visual feedback for low stock items, displays a user-friendly message when searches return no records, and includes Category information alongside Supplier information in search results.

## 2026-09-16

### Requirement 3 - Product Detail

Completed the Product Detail feature.

#### Views
- Created `product_detail(request, product_id)` in `views.py`.
- Used `get_object_or_404(Product, pk=product_id)` to retrieve a single product.
- Retrieved related order lines using:
  ```python
  product.orderdetail_set.all()

  ## 2026-09-17

### Requirement 3 - Product Detail

Completed Product Detail.

Implemented:

- Created `product_detail()` view.
- Added `product_detail_url`.
- Added Product Detail template (`product_detail.html`).
- Added Product Name links from Product List to Product Detail.
- Added Product Info card:
  - Product Name
  - Unit Price
  - Units In Stock
  - Discontinued Status
- Added Supplier & Revenue card:
  - Supplier Company
  - Supplier Contact
  - Units Sold
  - Total Revenue
- Added Order History table:
  - Order Number
  - Customer Name
  - Quantity
  - Line Total
- Added links from Order History to Order Detail page.

### Django Relationships Practiced

Used:

```python
product.supplier
product.orderdetail_set
line.order
order.customer