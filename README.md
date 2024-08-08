import pandas as pd
import matplotlib.pyplot as plt

file_path ="C:\\Users\\LENOVO\\Documents\\COVID 19 Cases in the Philippines.xlsx"  
sheet_name = 'Sheet1'

data = pd.read_excel(file_path, sheet_name=sheet_name)

print(data)
df = pd.DataFrame(data)

# Plotting Histogram
plt.figure(figsize=(10, 5))
n, bins, patches = plt.hist(df['Age'].dropna(), bins=10, edgecolor='black')
plt.hist(df['Age'].dropna(), bins=10, edgecolor='black')
plt.title('Age Distribution Histogram')
plt.xlabel('Age')
plt.ylabel('Frequency')
for i in range(len(patches)):
    plt.text(patches[i].get_x() + patches[i].get_width() / 2, n[i], int(n[i]), ha='center', va='bottom')
plt.show()

# Plotting Bar Chart
age_counts = df['Age'].value_counts().sort_index()

plt.figure(figsize=(10, 5))
age_counts.plot(kind='bar', edgecolor='black')
plt.title('Age Distribution Bar Chart')
plt.xlabel('Age')
plt.ylabel('Frequency')
plt.show()


# Plotting Histogram for Gender Distribution

df['Sex'] = df['Sex'].astype('category').cat.codes

plt.figure(figsize=(10, 5))
n, bins, patches = plt.hist(df['Sex'], bins=range(df['Sex'].nunique() + 1), edgecolor='black', align='left')
plt.hist(df['Sex'], bins=range(df['Sex'].nunique() + 1), edgecolor='black', align='left')
plt.title('Gender Distribution Histogram')
plt.xlabel('Gender (0: Female, 1: Male)')
plt.ylabel('Frequency')
plt.xticks(range(df['Sex'].nunique()), df['Sex'].astype('category').cat.categories)
for i in range(len(patches)):
    plt.text(patches[i].get_x() + patches[i].get_width() / 2, n[i], int(n[i]), ha='center', va='bottom')
plt.show()

# Plotting Bar Chart for Gender Distribution
gender_counts = df['Sex'].value_counts()

plt.figure(figsize=(10, 5))
bars = plt.bar(gender_counts.index, gender_counts.values, edgecolor='black')
plt.title('Gender Distribution Bar Chart')
plt.xlabel('Gender')
plt.ylabel('Frequency')

for bar in bars:
    yval = bar.get_height()
    plt.text(bar.get_x() + bar.get_width() / 2, yval, int(yval), ha='center', va='bottom')
    
plt.text(0.5, max(gender_counts.values) + 1, 'female: 0, male: 1', ha='center', va='bottom', fontsize=9)
plt.show()
