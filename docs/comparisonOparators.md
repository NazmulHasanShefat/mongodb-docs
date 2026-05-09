## 🔢 Comparison Operators — `$eq`, `$ne`, `$gt`, `$gte`, `$lt`, `$lte`

These operators let you filter data by comparing field values — just like searching "show me jobs with salary above 50,000."

| Operator | Meaning |
|----------|---------|
| `$eq` | Equal to |
| `$ne` | Not equal to |
| `$gt` | Greater than |
| `$gte` | Greater than or equal |
| `$lt` | Less than |
| `$lte` | Less than or equal |

### `$eq` — Equal

```js
// Jobs in Dhaka
db.jobs.find({ location: { $eq: "Dhaka" } })

// Shorthand (same result)
db.jobs.find({ location: "Dhaka" })
```

> **Tip:** `$eq` is MongoDB's default behavior. `{ field: value }` is equivalent.

### `$ne` — Not Equal

```js
// Jobs outside Dhaka
db.jobs.find({ location: { $ne: "Dhaka" } })
```

### `$gt` / `$gte` — Greater Than / Greater Than or Equal

```js
// Salary strictly above 70,000
db.jobs.find({ salary: { $gt: 70000 } })

// Salary 70,000 or above
db.jobs.find({ salary: { $gte: 70000 } })
```

### `$lt` / `$lte` — Less Than / Less Than or Equal

```js
// Entry-level jobs under 50,000
db.jobs.find({ salary: { $lt: 50000 } })

// 50,000 or below
db.jobs.find({ salary: { $lte: 50000 } })
```

### Combining Comparison Operators

```js
// Salary between 50,000 and 90,000
db.jobs.find({ salary: { $gte: 50000, $lte: 90000 } })

// Experience > 3 AND salary > 60,000
db.jobs.find({
  experience: { $gt: 3 },
  salary: { $gt: 60000 }
})
```

---