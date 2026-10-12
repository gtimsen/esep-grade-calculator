# ESEP Grade Calculator

This library is a simple utility to calculate your grades.

Runtime requirements:
Golang 1.24+

Run unit tests:
```
cd grade-calculator/
go test ./...
```

Run unit tests with code coverage:
```
cd grade-calculator/
go test -coverprofile=coverage.txt ./...
```

View coverage results:
```
go tool cover -func=coverage.txt
go tool cover -html=coverage.txt
```

How grades are calculated:
Each grade type (assignments, exams, essays) is averaged separately, then weighted:
Assignments 50%, Exams 35%, Essays 15%

Grade scale:
A >= 90, B >= 80, C >= 70, D >= 60, F < 60

Example usage:
```go
gc := NewGradeCalculator()
gc.AddGrade("hw 1", 95, Assignment)
gc.AddGrade("midterm", 88, Exam)
gc.AddGrade("essay 1", 90, Essay)
gc.GetFinalGrade() // returns "A"
```