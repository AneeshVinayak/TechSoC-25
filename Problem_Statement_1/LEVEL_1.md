shift = int(input("Enter the desired shift :"))
message = input('Enter the data to be encoded:')
shift = shift % 26
encrypted_words = ""
for word in message:
	for letter in word:
		a = ord(letter)
		if (96<a<(123 - shift)):
			b = a + shift
		elif((122 - shift)<a<123):
			b = 96 + shift
		elif (64<a<(91 - shift)):
			b = a + shift
		elif((65 - shift)<a<91):
			b = 65 + shift
		else:
			b = a
		encrypted_words += chr(b)
print('Encrypted message : ',encrypted_words)
real_words = ""
for word in encrypted_words:
	for letter in word:
		a = ord(letter)
		if ((97 + shift -1)<a<123):
			b = a - shift
		elif(96<a<(97+ shift)):
			b = a + 26 - shift
		elif ((65 + shift -1)<a<90):
			b = a - shift
		elif(64<a<(65+ shift)):
			b = a + 26 - shift
		else:
			b = a
		real_words += chr(b)
print('Decoded message : ',real_words)
