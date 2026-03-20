# 🍜 API Testing Lab: Auntie Som’s Noodle Stall

### Bugs I Found

1. **Price calculation is wrong**
   - Ordered Tom Yum (price 50) with quantity 1
   - API returned 45 instead of 50
   - So the system is subtracting something weird

2. **Can order more than stock**
   - Tried ordering way more than available stock
   - API still created the order
   - Stock system is broken

3. **Non-existent order returns 200**
   - When I request an order that doesn't exist
   - It returns 200 instead of 404
   - Not correct behavior

---

### Things that work correctly

- Login works and returns token
- Unauthorized request gives 401
- Invalid item gives 404
- Quantity 0 or negative gives 400

---

### How I tested

- Used Bruno to send requests
- Stored token from login
- Used values from menu (like itemId, price)
- Added tests to check:
  - status codes
  - total price
  - order creation logic

Some tests are failing on purpose because the system has bugs.