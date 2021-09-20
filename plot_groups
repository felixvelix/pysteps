import matplotlib.pyplot as plt
import random
def map_user_input(file_path, user_input = None):
  
    table = []
    with open(file_path) as csv_file:
        csvreader = csv.reader(csv_file, delimiter=";")
      
        fields = next(csvreader)
        for x in range(len(fields)):

            fields[x] = fields[x].replace(u"\ufeff", " ")

        for t in csvreader:
           

                table.append(t)
        for s in range(len(table)):
            for p in range(len(table[s])):
                table[s][p] = table[s][p].replace(" ","").replace(",",".").replace(u"\xa0","")
                if p > 1:
                    table[s][p] = float(table[s][p])*float(table[s][1])/100
        if user_input == "unter 20":
            new_table = []
            for s in range(len(table)):
                new_table.append([table[s][0], table[s][2]])
            return new_table
        if user_input == "20 bis 40":
            new_table = []
            for s in range(len(table)):
                new_table.append([table[s][0], table[s][3]])
            return new_table
        if user_input == "40 bis 60":
            new_table = []
            for s in range(len(table)):
                new_table.append([table[s][0], table[s][4]])
            return new_table
        if user_input == "60 bis 80":
            new_table = []
            for s in range(len(table)):
                new_table.append([table[s][0], table[s][5]])
            return new_table
        if user_input == "80 und mehr":
            new_table = []
            for s in range(len(table)):
                new_table.append([table[s][0], table[s][4]])
            return new_table
                    


    return table

age_group_data1 = map_user_input('../data/population_by_age_group.csv', "20 bis 40")
age_group_data2 = map_user_input('../data/population_by_age_group.csv', "60 bis 80")
age_group_data3 = map_user_input('../data/population_by_age_group.csv', "80 und mehr")

def visualize_data(y_and_p):
    years =[]
    p_counts = []
    all_years = []
    all_ps = []
    for ll in range(len(y_and_p)):
        years.append([])
        p_counts.append([])
        for i in range(len(y_and_p[ll])):
            years[ll].append(y_and_p[ll][i][0])
            p_counts[ll].append(y_and_p[ll][i][1])
            all_years.append(y_and_p[ll][i][0])
            all_ps.append(y_and_p[ll][i][1])

    plt.figure(dpi=128, figsize=(20, 10))
    for q in range(len(years)):
        r = random.random()
        b = random.random()
        g = random.random()
        color = (r, g, b)
        plt.plot(years[q], p_counts[q], '--' '+',  markersize=10,c=color)
    plt.xlabel('Year')
    plt.ylabel('Population')
    xmin, xmax = min(years[0]), max(years[0])
    ymin, ymax = min(all_ps), max(all_ps)
    plt.axis([xmin, xmax, ymin, ymax])
    plt.show()

visualize_data([age_group_data1, age_group_data2, age_group_data3])
