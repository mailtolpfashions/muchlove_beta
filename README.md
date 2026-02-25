# muchlove_beta
CRM and Billing Mobile App Beta
------------------------------------------------------------
Billing Page
------------------------------------------------------------
Features:

1. Add New Customer
2. Select Existing Customer
3. Recent Services
4. Quick Payment
5. Payment

Workflow Paths:
Create New Customer → Billing → Payment
Select Existing Customer → Billing → Payment
Quick Payment → Payment
Select Service → Billing → Select Customer/Create Customer → Payment

1. Add New Customer
User can add a new customer using Name and a valid unique Mobile Number.
Once added, the customer should be auto-selected to proceed to payment.

2. Select Existing Customer
User can search for a customer by name or mobile number using a search box.
After selection, the user can proceed to payment.

3. Recent Services
User can view the last 5 frequently billed services.
User must select a customer before proceeding to payment.

4. Quick Payment - In-Progress
User can proceed directly to payment by entering an amount.
Customer name is optional.

5. Payment
User can add, remove or remove all items from cart
User can choose select payment method, cash or online/UPI
User able to view proper error message or sale complete with invoice number 

------------------------------------------------------------
Sales Page :
------------------------------------------------------------
User can add filters in sales page, 
as a admin able to view filter values: today, yesterday, last week and this month.
this month means calendar month not last 30 days
by default selected today
and filter for cash and online/upi
and service and sales

employee only have todays and yesterday
and filter for cash and online/upi
and service and sales

------------------------------------------------------------
Settings Page :
------------------------------------------------------------
Features:
1. Profile
2. Management
	2.1. Inventory
	2.2. Staff
	2.3. Customers
3. Subscriptions
3.1 Subscription Plans
3.2 Customer Subscriptions
4. Offers
5. Payments
6. About Us
7. LogOut 

-----------------------------------------------------------
RUN
-----------------------------------------------------------
npx expo start --clear
eas build -p android --profile preview


failed. bun install --frozen-lockfile exited with non-zero code: 1

Try 
bun install --frozen-lockfile

Else
rm -rf node_modules bun.lockb
Remove-Item -Recurse -Force node_modules
Remove-Item bun.lockb

bun install

--------------------------------------------------------------
SUPABASE
-------------------------------------------------------------
Add Key:
eas secret:create --name EXPO_PUBLIC_SUPABASE_URL --value "https://ddaptndonmardgqyemah.supabase.co"
eas secret:create --name EXPO_PUBLIC_SUPABASE_ANON_KEY --value "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImRkYXB0bmRvbm1hcmRncXllbWFoIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NzE3NDI1MDIsImV4cCI6MjA4NzMxODUwMn0.1cTPWkQhB6nF5OcJIraxl8nbvRQ-JmWvC5q5g1oES30"


Delete Key:
eas env:delete preview --variable-name EXPO_PUBLIC_SUPABASE_ANON_KEY
eas env:delete preview --variable-name EXPO_PUBLIC_SUPABASE_URL


-- Run this in Supabase SQL Editor if the app did not seed users (e.g. RLS blocking).
-- Log in with: admin / admin123  or  employee / emp123


EVN:
EXPO_PUBLIC_SUPABASE_URL=https://ddaptndonmardgqyemah.supabase.co
EXPO_PUBLIC_SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImRkYXB0bmRvbm1hcmRncXllbWFoIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NzE3NDI1MDIsImV4cCI6MjA4NzMxODUwMn0.1cTPWkQhB6nF5OcJIraxl8nbvRQ-JmWvC5q5g1oES30


INSERT INTO users (id, username, password_hash, name, role, created_at) VALUES
  ('seed_admin_1', 'admin', 'veeet2c8e6', 'Administrator', 'admin', now()),
  ('seed_employee_1', 'employee', 'vs6h1w80ks', 'Staff Member', 'employee', now())
ON CONFLICT (username) DO NOTHING;
