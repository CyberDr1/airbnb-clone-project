# Database Normalization – Airbnb Clone

## Objective:
Apply normalization principles to ensure the database is in **Third Normal Form (3NF)**.

---

## First Normal Form (1NF)
**Goal:** Eliminate repeating groups; ensure each field contains atomic (indivisible) values.

 Each table has a primary key.  
 All columns contain only atomic values.  
 No repeating groups.

---

## Second Normal Form (2NF)
**Goal:** Remove partial dependencies (non-key columns should depend on the whole primary key).

 All tables have single-column primary keys (or full composite keys used properly).  
 All non-key attributes fully depend on the primary key.

---

## Third Normal Form (3NF)
**Goal:** Remove transitive dependencies (non-key attributes should depend only on the primary key).

 No transitive dependencies exist.  
 Each non-key column is only dependent on the table’s primary key.

---

## Example Schema Review and Adjustments

### Entity: Property

| id | title | owner_id | owner_email | city |
|----|-------|----------|-------------|------|

 `owner_email` depends on `owner_id`, not `Property.id` → **transitive dependency**

### Solution:
Move `owner_email` to the `User` table (where `owner_id` belongs).

---

## Summary of Changes

- Removed `owner_email` from `Property` table.
- Ensured each entity follows:
  - Atomic columns
  - Proper primary/foreign keys
  - No transitive dependencies

---

## Conclusion

The schema has been adjusted to comply with **3NF**, ensuring:
- Data integrity
- Minimal redundancy
- Easier maintenance