# file-handling-and-exception-handling
def read_and_modify_file():
    # Ask user for filename
    filename = input("Enter the filename to read: ")

    try:
        # Open file for reading
        with open(filename, "r") as file:
            content = file.readlines()  # Read all lines
        
        # Modify the content (Example: Convert to uppercase)
        modified_content = [line.upper() for line in content]
        
        # Write to a new file
        new_filename = "modified_" + filename
        with open(new_filename, "w") as new_file:
            new_file.writelines(modified_content)
        
        print(f"Modified content saved to {new_filename}")

    except FileNotFoundError:
        print("❌ Error: The file does not exist.")
    except IOError:
        print("❌ Error: Unable to read the file.")
    except Exception as e:
        print(f"⚠️ Unexpected error: {e}")

# Run the function
read_and_modify_file()
