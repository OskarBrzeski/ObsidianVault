Query an SQL database
```go
func getRows(dbPointer *sql.DB, salary int) ([]Row, error) {
	query = "SELECT id, title FROM table WHERE salary=?;"

	rows, err := dbPointer.Query(query, salary)
	if err != nil {
		return nil, err
	}
}
```

Iterate over rows
```go
var exampleArray []Row

for rows.Next() {
	var example Row
	
	err := rows.Scan(&example.id, &example.title)
	if err != nil {
		return nil, err
	}

	exampleArray = append(exampleArray, example)
}

if err = rows.Err(); err != nil {
    return nil, err
}

return exampleArray, nil
```

Check how many rows were changed by query
```go
result, _ := dbPointer.Exec(query)

rowsChanged, err := result.RowsAffected()
```

