# Caesar-Cipher

---

### Overview
In cryptography, a Caesar cipher, also known as the shift cipher, is one of the simplest and most widely known encryption techniques. It is a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet to create the ciphertext. For example, with a left shift of 3, D would be replaced by A, E would become B, and so on. The method is named after Julius Caesar, who used it in his private correspondence.

During Caesar's time, most people could not read, so sending a message in written form would be some measure of security.  However, Caesar added a layer of encipherment by means of substitution.  This may well have made the messages uncrackable, as there is no evidence of any techniques as the time to solve substitution ciphers.  In modern practice, however, this method of encipherment offers almost no communication security.  It does, however, have application in other ciphers, including the modern ROT13 system.  And when different encryption techniques are layered, it provides greatly increased layers of protection.

### Instructions

This is a multistep assignment:

0. Preferably, the text should be received through a `.txt` file.  Create or use a class (or module) that can read a string from a text file, and write to a text file.  If this is not possible, the text to be used should be stored in a separate `.py` file.


1. Create a **`CaesarShift`** module[^1] that is able to receive a word or character and performs a shift on the object the requested number of positions.  Letters should retain their case, while all other characters should remain unaffected.  For example, if the word is *"Sesquipedalian"* and the shift is 1, the result will be *"Tftrvjqfebmjbo"*.


2. An **`Encipher`** class will receive a string (from the file created in step 0) and will perform use **`CaesarShift`** to modify the text a user-decided number of positions.  The altered text will be saved, preferably using the class created in step 0. 


3. The **`Encipher`** class can be run with the inverse of the number to decipher a text.  However, if the key is unknown, the task of deciphering the text is more difficult.  In a **`Decipher`** class, create the logic that attempts to solve what the plaintext should be.  Each attempt against the ciphertext should be tested against a dictionary to see if contains valid words and if it may be the correct plaintext.  The dictionary does not need to be extensive; it just needs to allow the program to function correctly.  When the program believes it has the correct text, it should write it to a file.  You may attempt to decipher the text any way you want, but must check it against the dictionary.

    Note:  You will need to sanitize your decrypted text to check it against the dictionary.

---

### Documents

There are six text documents contained within the documents folder.  They are:
* **01a_Example_input** and **01b_Example_output** - an example of what an input with a backward shift of 3 (or forward shift of 23) returns as an output.
* **02a_Encryption_input** and **02b_Encryption_target** - the input file is to be run through **`Encipher`** class with a forward shift of 1 and written to a file named **01c_Encryption_output**.  The target file shows the expected output.
* **03_Decryption_input** - the document you are to decipher.  You must decide on the technique you will use to decrypt the cipher.
* **3000_Common_English_words** - contains the list of words you will use to test if decryption is successful.

---
#### Footnotes

[^1]: Python can work as both a functional and object-oriented programming language.  What we wish to do here is use the object-oriented side, while not incurring the normal expense.  Normally, when creating a class (e.g. any class that has an `__init__` method), the computer must spend resources to both instantiate the class (create it) and house it for the lifetime of its use.<br>
  **`CaesarShift`** does not need to be created every time it is to be used.  It can be used by multiple classes with no difference in results.  It retains no information itself, but receives, manipulates, and returns the data without remembering any.<br>
  For a normal class, when a program is compiled, the class object is not created.  If we use a `Car` class as an example, it is only when a new object of the class is created (`car = Car()`) would a new instance of `Car` be created.  A second instance of the object can be created (`car_2 = Car()`), and a third, etc.  Each one of these must be created and stored.<br>
  This is not what we want for **`CaesarShift`**.  Many programming languages contain a **static** keyword, which allows a variable, method, or class to have only one existence.  Instead of creating multiple objects, when the program is compiled, one instance of this static object is created and stored.  All references to this object point to this, which saves on both space and time, as only one instance is ever created for runtime.<br>
  Although Python does not possess **static**, similar behavior can be invoked by creating **`CaesarShift`** as a module rather than a class.  Like the **`turtle`** and **`math`** modules, it can be imported and its methods used directly.  Under a file the encompassing module name (like **`math`**), all methods definitions are written directly to the file, without using the `class` keyword.

