import os
import socket
from collections import Counter

# Path to the directory containing the text files
data_dir = '/home/data'

# Path to the output file
output_file = '/home/output/result.txt'

# Create the output directory if it doesn't exist
os.makedirs(os.path.dirname(output_file), exist_ok=True)

# List name of all the text files at location: /home/data
files = os.listdir(data_dir)
print("Files:")
for file in files:
    print(file)

# Read the two text files and count total number of words in each text file
total_words = 0
for file_name in ['IF.txt', 'Limerick-1.txt']:
    with open(os.path.join(data_dir, file_name), 'r') as f:
        content = f.read()
        words = content.split()
        num_words = len(words)
        total_words += num_words
        print(f"\nNo. of words in {file_name}: {num_words}")

# Add all the number of words to find the grand total
print(f"\n total words: {total_words}")

# List the top 3 words with maximum number of counts in IF.txt
if 'IF.txt' in files:
    with open(os.path.join(data_dir, 'IF.txt'), 'r') as f:
        content = f.read()
        words = content.split()
        word_counts = Counter(words)
        top_words = word_counts.most_common(3)
        print("\nTop 3 words with max. counts in IF.txt:")
        for word, count in top_words:
            print(f"{word}: {count}")

# Find the IP address of the machine
hostname = socket.gethostname()
ip_address = socket.gethostbyname(hostname)
print(f"\nIP address: {ip_address}")

# Write all the output to a text file at location: /home/output/result.txt
with open(output_file, 'w') as f:
    f.write("Files:\n")
    for file in files:
        f.write(f"{file}\n")
    f.write("\n")
    for file_name in ['IF.txt', 'Limerick-1.txt']:
        with open(os.path.join(data_dir, file_name), 'r') as file_content:
            content = file_content.read()
            words = content.split()
            num_words = len(words)
            f.write(f"No. of words in {file_name}: {num_words}\n")
    f.write(f"\n total words: {total_words}\n")
    if 'IF.txt' in files:
        f.write("\nTop 3 words with max. counts in IF.txt:\n")
        for word, count in top_words:
            f.write(f"{word}: {count}\n")
    f.write(f"\nIP address: {ip_address}\n")

# Print the output
with open(output_file, 'r') as f:
    print("\nOutput written to result.txt:")
    print(f.read())
