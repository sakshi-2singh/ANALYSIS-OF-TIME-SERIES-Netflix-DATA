# ANALYSIS-OF-TIME-SERIES-Netflix-DATA

import csv

def read_column_from_csv(filename, column_index):
    column_data = []
    with open(filename, 'r') as file:
        reader = csv.reader(file)
        for row in reader:
            if len(row) > column_index:
              if row[column_index] == 'Close':
                continue
              else:
                column_data.append(float((row[column_index])))
    return column_data

# Example usage
filename = '/content/drive/MyDrive/archive (10)/NFLX.csv'  # Replace with the actual filename or path
column_index = 4  # Replace with the index of the column you want to extract (zero-based)
column_data = read_column_from_csv(filename, column_index)
#column_data.pop(0)    ##Useless
print(column_data)
