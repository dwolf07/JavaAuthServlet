# JavaAuthServlet
Sample servlet with all keys

I've exposed the token generation in the doGet method, which is NOT recommended for production. This just makes it easy to generate a token and make sure all the fields are present and the values are set correctly using a browser.

To use it:
- Copy the layer.pk8 file somewhere safe
- In IdentityTokenGenerator.java, point to that .pk8 file
- Launch the web service
- Connect to the server to generate an identity token like so:

http://localhost:8080/hello?nonce=somenonce&user_id=myuserid

And this Identity Token should be generated:

{"identity_token":"eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXUyIsImN0eSI6ImxheWVyL
WVpdDt2XHUwMDNkMSIsImtpZCI6IjMxMTU5NGYyLWQ4MDAtMTFlNC05MTg5LWRlMjE5ZDAwM
2E0MCJ9.eyJpc3MiOiJiZjA5OGU5NC04NDkwLTExZTQtYmU0Zi1mY2YzNjEwNTQyNDkiLCJw
cm4iOiJteXVzZXJpZCIsImlhdCI6MTQyNzkxMzA4MywiZXhwIjoxNDI3OTEzMTQzLCJuY2Ui
OiJzb21lbm9uY2UifQ.lAH9KgOWqUWWz_AymUi7WcuhKsO0Ox0bpDEEQVSPZZDnXASqN7K4S
44Vd0q1oAguCXidv-KCosiCRZzTjPnVSSCgLG__v9izs995agDnBfzB3VaFJ-HraGhRMznMo
NxlRNIbsJmBvrMxTUMHNYLGb4ITnkrPDo7AiLKr9jWs3_Q"}

If you dump this into the Validation Tool in the Dashboard, keep in mind that you will get an error since the Provider ID is not associated with your account. That doesn't matter, as long as all the header fields are present.
