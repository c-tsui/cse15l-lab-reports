# Part 1
<img width="775" alt="string server code" src="https://user-images.githubusercontent.com/122579894/215379290-94e4e2b1-91fc-44aa-9459-e60f2be7a4e8.png">

<img width="400" alt="add message 1" src="https://user-images.githubusercontent.com/122579894/215379306-46696284-d079-4fe5-a9ed-c0fecdc41bce.png">

- method: ` public String handleRequest(URI url) `
- argument: URI url
  values: " ", "line1", URI("http://localhost:4000"), 4000
- String str " " changes when addedStr is added, String addedStr "line1" changes according to what message is added, int port 4000 usually doesn't change since it's 4000 by convention   

<img width="396" alt="add message 2" src="https://user-images.githubusercontent.com/122579894/215379313-c50a59ac-273e-41f3-910f-f50df8ff5bac.png">

- method: ` public String handleRequest(URI url) `
- argument: URI url
  values: "line1", "line2", URI("http://localhost:4000"), 4000
- String str "line1" changes when addedStr is added, String addedStr "line2" changes according to what message is added, int port 4000 usually doesn't change since it's 4000 by convention 

# Part 2
- a failure-inducing input: ` {1, 2, 3, 4, 5} `
- an input that doesn’t induce a failure: ` {3, 3, 3} `
- symptom: ` {5, 4, 3, 4, 5} ` and ` {3, 3, 3} `, respectively
- before:

