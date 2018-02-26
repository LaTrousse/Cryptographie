# Vigenere Cipher
Inputs plaintext and key;

# Variables
Declare an array of integer tupe named plaintext_int
Declare an array of letters type maned ciphertext
Set ciphertext size to size(plaintext)
Declare an integer letter_number
Set letter_number to 0
Declare an array of integer type named key_shift;  <!-- store the key as an array of integers and repeat it until it is as long as the plaintext-->
Declare an integer variable loopcounter;

#Key construction <!-- converting the string key to an array of integers to manipulate more easily -->
Set key_shift size to size(plaintext_int)
set loopcounter to 0
for loopcounter = 0 to size(plaintext_int)-1
  key_shift[loopcounter]= position of key[loopcounter mod size(key)] in the alphabet <!-- take loopcounter mod size(key) so the key is repeated in the array to have the same size as the plaintext -->
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
  letter_number = plaintext_int[loopcounter] + key_shift[loopcounter] mod 26 <!-- encrypt as integers = take the sum mod 26 of the plaintext and the key -->
  ciphertext[loopcounter] = letter in the position number (letter_number+1) in the alphabet <!-- going back to letters -->
end for

Output ciphertext converted to string
