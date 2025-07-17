import pandas as pd
from io import StringIO

# Simulated CSV data
csv_data = StringIO("""
Name,Math,Science,English
Alice,85,90,88
Bob,78,75,80
Charlie,92,85,87
David,70,65,72
Eva,88,95,91
""")

# Load CSV into DataFrame
df = pd.read_csv(csv_data)

# Show full dataset
print("Student Marks:\n", df)

# Calculate average marks for each student
df["Average"] = df[["Math", "Science", "English"]].mean(axis=1)

# Print top 3 students
print("\nTop 3 Students by Average Marks:\n", df.sort_values(by="Average", ascending=False).head(3))
#Slincing
print(df[:3])
Student Marks:
       Name  Math  Science  English
0    Alice    85       90       88
1      Bob    78       75       80
2  Charlie    92       85       87
3    David    70       65       72
4      Eva    88       95       91

Top 3 Students by Average Marks:
       Name  Math  Science  English    Average
4      Eva    88       95       91  91.333333
2  Charlie    92       85       87  88.000000
0    Alice    85       90       88  87.666667
print(df[:3])
Name  Math  Science  English    Average
0    Alice    85       90       88  87.666667
1      Bob    78       75       80  77.666667
2  Charlie    92       85       87  88.000000
print(df[["Name", "Math"]])
      Name  Math
0    Alice    85
1      Bob    78
2  Charlie    92
3    David    70
4      Eva    88
print(df.iloc[1:4])
Name  Math  Science  English    Average
1      Bob    78       75       80  77.666667
2  Charlie    92       85       87  88.000000
3    David    70       65       72  69.000000
print(df.iloc[0:3, 1:4])
Math  Science  English
0    85       90       88
1    78       75       80
2    92       85       87
print(df[df["Math"]>85])
Name  Math  Science  English    Average
2  Charlie    92       85       87  88.000000
4      Eva    88       95       91  91.333333
print(df.sort_values(by="Average",ascending=False).head(3))
Name  Math  Science  English    Average
4      Eva    88       95       91  91.333333
2  Charlie    92       85       87  88.000000
0    Alice    85       90       88  87.666667
df[df["Average"] < df["Average"].mean()]
Name	Math	Science	English	Average
1	Bob	78	75	80	77.666667
3	David	70	65	72	69.000000



