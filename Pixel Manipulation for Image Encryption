from PIL import Image
import time
def encrypt_image(image_path, output_path, key):
    print("Encrypting...")
    time.sleep(2) 
    with Image.open(image_path) as img:
        img = img.convert("RGB")  # Ensure image is in RGB mode
        pixels = img.load()
        
        for i in range(img.width):
            for j in range(img.height):
                r, g, b = pixels[i, j]
                r = (r + key) % 256
                g = (g + key) % 256
                b = (b + key) % 256
                pixels[i, j] = (r, g, b)
        
        img.save(output_path)
        print(f"Encrypted image saved as {output_path}\n")

def decrypt_image(image_path, output_path, key):
    print("Decrypting...")
    time.sleep(2)
    with Image.open(image_path) as img:
        img = img.convert("RGB")  # Ensure image is in RGB mode
        pixels = img.load()
        
        for i in range(img.width):
            for j in range(img.height):
                r, g, b = pixels[i, j]
                r = (r - key) % 256
                g = (g - key) % 256
                b = (b - key) % 256
                pixels[i, j] = (r, g, b)
        
        img.save(output_path)
        print(f"Decrypted image saved as {output_path}\n")

def img_manipulation():
    while True:
        option = input('''Enter the option:-
            1 for Encrypt
            2 for Decrypt
            3 for Exit\n''')
        
        if option not in ["1", "2",'3']:
            print("Invalid option. Please enter 1 or 2.\n")
            continue
        if option == "3":
            print("Exiting......")
            break
        
        image_path = input("Enter the image path:\n ")
        
        output_path = input("Enter the output image path:\n ")
        try:
            key = int(input("Enter the encryption/decryption key (1 - 256):\n "))
        except ValueError:
            print("Invalid key. Please enter an integer.")
            continue
        
        if option == "1":
            encrypt_image(image_path, output_path, key)
        elif option == "2":
            decrypt_image(image_path, output_path, key)
 
print("WELCOME TO THE IMAGE ENCRYPTION & DECRYPTION TOOL\n")
img_manipulation()
