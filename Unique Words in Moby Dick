import string

def build_count(word, text_dic):
    if word in text_dic:
        text_dic[word] = text_dic[word] + 1
    else:
        text_dic[word] = 1
    
def clean_word(line):
    line = line.strip()
    line = line.lower()
    line = line.translate(line.maketrans("", "", string.punctuation))
    words = line.split(" ")
    return words

def unique_words(text_dic):
    unique_list = []
    for key in list(text_dic.keys()):
        if text_dic[key] == 1:
            unique_list.append(key)
    return unique_list


def main():
    welcome = "Welcome to the word counter!"
    print(welcome.center(50,'='))
    file_name = input("Enter a file name: ")
    if file_name == "mobydick.txt":
        moby_file = open("mobydick.txt", "r")
        
        text_dic = dict()
    
        for line in moby_file:
            clean_word(line)
            for word in clean_word(line):
                build_count(word, text_dic)

        output_file1 = open("word_data.txt", "w")
        for key in list(text_dic.keys()):
            output_file1.write(str(key) + " : " + str(text_dic[key]) + "\n")
        output_file1.close()

        
        output_file2 = open("unique_words.txt", "w")
        output_file2.write("Here is a list of words that appear exactly one time in mobydick.txt:\n")
        for line in unique_words(text_dic):
            output_file2.write("\n" + str(line))
        output_file2.close()

        
        moby_file.close()
        print("The file mobydick.txt has been processed.")
        print("Output stored in word_data.txt and unique_words.txt")
        print("Exiting...")
    else:
        print("No such file exists.")


main()
