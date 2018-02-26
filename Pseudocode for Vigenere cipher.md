# Vigenere Cipher
Inputs plaintext and key;

# Variables
Declare an array of integer tupe named plaintext_int
Declare an array of character type maned ciphertext
Set ciphertext size to size(plaintext)
Declare an integer letter_number
Set letter_number to 0
Declare an array of integer type named key_shift;  <!-- store the shifts as integers, letter by letter of the key -->
Declare an integer variable loopcounter;

#Key construction <!-- converting the string key to an array of integers to manipulate more easily -->
Set key_shift size to size(key)
set loopcounter to 0
for loopcounter = 0 to size(key)-1
  key_shift[loopcounter]= position of key[loopcounter] in the alphabet
end for

#plaintext construction <!-- converting the string plaintext to an array of integers to manipulate more easily -->
Set plaintext_int size to size(plaintext)
set loopcounter to 0
for loopcounter = 0 to size(plaintext)-1
  plaintext_int[loopcounter]= position of plaintext[loopcounter] in the alphabet
end for

#Encryption
set loopcounter to 0
for loopcounter = 0 to size(plaintext_int-1)
    letter_number = plaintext_int[loopcounter] + key_shift[loopcounter mod size(key)]
    ciphertext[loopcounter] = letter in the position number (letter_number+1) in the alphabet
end for

Output ciphertext converted to string
