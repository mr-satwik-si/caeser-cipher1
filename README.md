# caeser-cipher1
caeser cipher 
alphabets=['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j',
 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't',
 'u', 'v', 'w', 'x', 'y', 'z']
def encrypt(original_text,shift_amt):
    display = ""
    for letter in original_text:
        if letter not in alphabets:
            newletter=letter
            display+=newletter
        else:
            new=alphabets.index(letter)+shift_amt
            if new<=25:
                newletter=alphabets[new]
                display+=newletter
            else:
                new=new-26
                newletter = alphabets[new]
                display+=newletter
    print(f"encoded result is:{display}")

def decrypt(original_text,shift_amt):
    display = ""
    for letter in original_text:
        if letter not in alphabets:
            newletter = letter
            display += newletter
        else:
            new=alphabets.index(letter)-shift_amt
            newletter=alphabets[new]
            display+=newletter
    print(f"decoded result is:{display}")
def caeser(encode_or_decode):
    if encode_or_decode=="encode":
        encrypt(original_text=text,shift_amt=shift)
    elif encode_or_decode=="decode":
        decrypt(original_text=text,shift_amt=shift)
should_continue=True
while should_continue:
    direction=input("type 'encode' to encrypt and 'decode'to decrypt:\n").lower()
    text=input("type ur message:\n").lower()
    shift=int(input("type the shift number :\n"))
    caeser(direction)
    abc=input("type 'yes' to continue and 'no' to stop")
    if abc=="yes":
        should_continue=True
    else:
        should_continue=False
