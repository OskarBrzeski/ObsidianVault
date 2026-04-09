```go
func SendEmail() {
	emailFrom := "from.address@example.com"
	emailTo := "to.address@example.com"
	emailBase := "example.com"
	emailPassword := "password123"
	
	from := "From: " + emailFrom + "\n"
	to := "To: " + emailTo + "\n"
	subject := "Subject: Learning about Emails from Go\n"
	headers := "MIME-version: 1.0;\nContent-Type: text/html; charset=\"UTF-8\";\n\n"
	content := "This is an example email message."

	msg := from + to + subject + headers + content

	auth := smtp.PlainAuth(
		"",
		emailFrom,
		emailPassword,
		emailBase,
	)

	err := smtp.SendMail(
		emailBase+":587",
		auth,
		emailFrom,
		[]string{emailTo},
		[]byte(msg)
	)
	if err != nil {
		fmt.Println(err)
	}
}
```