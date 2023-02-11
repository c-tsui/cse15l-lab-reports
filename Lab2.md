# Part 1
<img width="775" alt="string server code" src="https://user-images.githubusercontent.com/122579894/215379290-94e4e2b1-91fc-44aa-9459-e60f2be7a4e8.png">

<img width="400" alt="add message 1" src="https://user-images.githubusercontent.com/122579894/215379306-46696284-d079-4fe5-a9ed-c0fecdc41bce.png">

- method: ` public String handleRequest(URI url) `
- argument: URI url
  - values: "/add-message?=", string addedStr, string str, and "\n"
- String str changes according to what message is added

<img width="396" alt="add message 2" src="https://user-images.githubusercontent.com/122579894/215379313-c50a59ac-273e-41f3-910f-f50df8ff5bac.png">

- method: ` public String handleRequest(URI url) `
- argument: URI url
  - values: "/add-message?=", string addedStr, string str, and "\n"
- String str changes when addedStr is added, and string addedStr changes according to what message is added

# Part 2
The buggy code is in a method called reverseInPlace from lab3.
- a failure-inducing input: ` {1, 2, 3, 4, 5} `
  - symptom: ` {5, 4, 3, 4, 5} `
- an input that doesn’t induce a failure: ` {3, 3, 3} `
- before:
```
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}
```
<img width="901" alt="Screen Shot 2023-02-11 at 12 19 11 PM" src="https://user-images.githubusercontent.com/122579894/218280196-4b4cc914-8a4a-48d4-ad95-475d1929a0fa.png">

- after:
```
static void reverseInPlace(int[] arr) {
  int[] newArray = new int[arr.length];
  for(int i = 0; i <arr.length; i += 1) {
    newArray[i] = arr[arr.length - i - 1];
  }
  for(int i = 0; i < arr.length; i += 1){
    arr[i]=newArray[i];
  }
}
```
<img width="900" alt="Screen Shot 2023-02-11 at 12 15 53 PM" src="https://user-images.githubusercontent.com/122579894/218280210-3175e8e6-c186-4511-88a8-dda2ef8b5e58.png">

The issue for failure-inducing input is that the value in the resulted array was modified not according to the original order but the order after reversing, take the above input for example, the first two values. In this case, the last two values were assigned to the modifies values, not the original values we wished to assigned. Therefore, I create an empty array so that the order will not be affect by previous assigned values. The reversed value then can be assigned to specific position without being modified before hand. 

# Part 3 
Everything I learned in week 2 and 3 was very new to me. I've never learned, for example, running a server and remotely connected to a computer. It's very interesting to write down a code that  builds my own search engine. 

