encrypt.py
import string

def caesar_cipher(text, distance):
    encrypted_text = ""
    all_chars = string.printable  # All printable ASCII characters
    char_count = len(all_chars)
    
    for char in text:
        if char in all_chars:
            new_index = (all_chars.index(char) + distance) % char_count
            encrypted_text += all_chars[new_index]
        else:
            encrypted_text += char  # Leave unchanged if not in printable set
    
    return encrypted_text

if __name__ == "__main__":
    plaintext = input("Enter plaintext: ")
    distance = int(input("Enter distance value: "))
    encrypted = caesar_cipher(plaintext, distance)
    print("Encrypted text:", encrypted)

decrypt.py
import string

def caesar_decipher(text, distance):
    decrypted_text = ""
    all_chars = string.printable  # All printable ASCII characters
    char_count = len(all_chars)
    
    for char in text:
        if char in all_chars:
            new_index = (all_chars.index(char) - distance) % char_count
            decrypted_text += all_chars[new_index]
        else:
            decrypted_text += char  # Leave unchanged if not in printable set
    
    return decrypted_text

if __name__ == "__main__":
    encrypted_text = input("Enter encrypted text: ")
    distance = int(input("Enter distance value: "))
    decrypted = caesar_decipher(encrypted_text, distance)
    print("Decrypted text:", decrypted)

copyfile.py
def copy_file(source_file, destination_file):
    try:
        with open(source_file, 'r') as src:
            content = src.read()
        
        with open(destination_file, 'w') as dest:
            dest.write(content)
        
        print(f"Contents copied from {source_file} to {destination_file}")
    except FileNotFoundError:
        print("Error: Source file not found.")
    except Exception as e:
        print(f"An error occurred: {e}")

if __name__ == "__main__":
    source = input("Enter the name of the source text file: ")
    destination = input("Enter the name of the destination text file: ")
    copy_file(source, destination)
