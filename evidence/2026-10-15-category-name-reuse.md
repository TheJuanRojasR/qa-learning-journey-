# Cannot create a category with the same name as a deleted category

*Bug report — model version · found 2026-10-15 (practice app, local) · reviewed in strict mode 2026-10-17*

**Environment:** Linux (Ubuntu 26.04.1) · Chrome 155.0.8059.39 · App local v1.0.0

**Preconditions:** You are logged in as the default user (email: user@email.com · password: user.1234).

**Steps to reproduce:**

1. Click "Categories".
2. Click "Create new category".
3. Type "Sport" in the category name field and click "Create category".
4. Select the "Sport" category and click "Delete category".
5. Click "Confirm".
6. Click "Create new category".
7. Type "Sport" again in the category name field and click "Create category".

**Expected result:** The category is created successfully — the name should be available again.

**Actual result:** The category is not created. A modal appears with the message "No se puede crear una categoría existente con el mismo nombre."

**Severity:** Medium — it does not block the main workflow, but there is no way to reuse the name of a deleted category.
