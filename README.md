# BotBazaar
## Business Rule
## 1.	Admin
-	Attributes: admin_id, user_id, admin_name, email, password, phone_number, address.
-	An admin manages users, products, and platform settings.
-	An admin can add, delete, and update user as well as vendor accounts.
-	An admin has permission to generate reports and access user profile management.
- Only an admin can approve new vendor registrations and the addition of new products.
- Uniqueness: The admin must have a unique email and phone_number.
-	Mandatory: admin_id, user_id, admin_name, email, password, phone_number and address.

## 2.	User
-	Attributes: user_id, user_name, email, password, phone_number, address, role, date_joined.
-	A user can register as a buyer, vendor, or admin.
-	A user can add items to the cart and proceed the order after payment.
-	A user can browse different products and give reviews too.
-	A user can give ratings to both the products and the vendor.
-	A user has access to its order history, reviews, and notifications.
-	Uniqueness: Users must provide unique email and phone number for registration.
-	Mandatory: user_name, password, address, role, date_joined

## 3.	Vendor
-	Attributes: vendor_id, user_id, store_name, store_logo, rating, date_registered, license_image, address.
-	A vendor must provide a valid business license before registration.
-	A vendor can create, update and delete their own product listings.
-	A vendor should check and update its inventory regularly.
-	Uniqueness: Vendors must provide unique email, phone number and license number.
-	Mandatory: vendor_id, store_name, date_registered, address, license_image.
-	Optional: store_logo

## 4.	Product:
-	Attributes: product_id, vendor_id, discount_id, product_category_id, product_name, product_description, product_image, product_price, stock_quantity, product_tags, date_added.
-	Each product must belong to a single product category.
-	A product must include at least one image and a description.
-	A product cannot be purchased if its stock quantity is zero.
-	Uniqueness: A product must have a unique product id.
-	Mandatory: product_id, vendor_id, product_category_id, product_name, product_description, product_image, product_price, stock_quantity, date_added.

## 5.	Product_category:
-	Attributes: product_category_id, product_category_name, description.
-	A product belongs to only one product category but may have multiple tags for search optimization.
-	It provides ease of access by grouping related products.
-	Uniqueness: Each product_category must have a unique name and a description.
-	Mandatory: product_category_id, product_category_name, description.

## 6.	Order:
-	Attributes: order_id, user_id, order_date, order_status, total_amount.
-	An order must belong to one user.
-	An order must have a payment status and cannot be shipped until payment is completed.
-	Uniqueness: Each order must have a unique order_id.
-	Mandatory: order_id, user_id, order_date, order_status, total_amount.

## 7.	Cart:
-	Attributes: cart_id, user_id, product_id, total_quantity, total_price.
-	A cart belongs to only one user.
-	A cart’s total amount must be recalculated after every update.
-	Uniqueness: A cart must have a unique cart_id.
-	Mandatory: cart_id, user_id, product_id, total_quantity, total_price.

## 8.	Payment:
-	Attributes: payment_id, order_id, payment_status, payment_method, total_amount, payment_date.
-	A cart belongs to only one user.
-	A cart’s total amount must be recalculated after every update.
-	Uniqueness: A payment must have a unique payment_id.
-	Mandatory: payment_id, order_id, payment_status, payment_method, total_amount, payment_date.

## 9.	Notification:
-	Attributes: notification_id, user_id, message, created_date.
-	Notifications can be sent to users, vendors, and admin.
-	Vendors will automatically receive notifications about new orders, payments, and customer reviews.
-	Uniqueness: A payment must have a unique payment_id.
-	Mandatory: payment_id, order_id, payment_status, payment_method, total_amount, payment_date.

## 10. Report:
-	Attributes: report_id, report_type, report_details, created_date.
-	Reports must be stored securely and cannot be altered after creation.
-	Uniqueness: A report must have a unique report_id.
-	Mandatory: report_id, report_type, report_details, created_date.

## 11. Review:
-	Attributes: review_id, user_id, product_id, review_text, review_date, rating.
-	User can review many products.
-	Only one review per user per product purchase is allowed.
-	Uniqueness: A report must have a unique report_id.
-	Mandatory: review_id, user_id, product_id,  review_date, rating.
-	Optional: review_text.

## 12. Discount:
- Attributes: discount_id, discount_code, product_id, discount_percentage, usage_limit, code_expiry_date.
- Providing users with discount coupons and codes.
- A discount can be applied to multiple products, but each product can have only one active discount at a time.
- Uniqueness: Each discount must have a unique discount_code.
- Mandatory: discount_id, discount_code, product_id, discount_percentage, usage_limit, code_expiry_date.
