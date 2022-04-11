# authServer

This is a simple golang based server which provides authorisation. Based on a article by [Sanad Haj](https://medium.com/@hajsanad/authentication-in-golang-using-go-guardian-b1cd47da47a0)

## Building 

For easy try out we provide a dockerfile. To build and run use

    docker build -t authserver . 
    docker run -p 8080:8080 authserver

This makes the service available at port 8080

## Usage

To test the API and/or make use of it 

    curl  -k http://127.0.0.1:8080/v1/book/3453164172 -u tub:tub
    Author: Isaac Asimov

To obtain a token

    curl  -k http://127.0.0.1:8080/v1/auth/token -u tub:tub
    token: b11d1e98-5d2e-4d56-89f8-415b68fdbd74

Getting a book via the API 

    curl  -k http://127.0.0.1:8080/v1/book/3453164172 -H "Authorization: Bearer b11d1e98-5d2e-4d56-89f8-415b68fdbd74"
    Author: Isaac Asimov

