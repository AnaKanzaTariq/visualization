import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load dataset
df = pd.read_csv("mci_ontario_bridge_training_program.csv")

# Clean grant amount column
df['Grant Amount'] = df['Grant Amount'].replace('[\$,]', '', regex=True).astype(float)

# Aggregate total funding by organization
org_funding = df.groupby('Organization Name')['Grant Amount'].sum().sort_values(ascending=False)

# Plot
plt.figure(figsize=(12, 18))
sns.barplot(x=org_funding.values, y=org_funding.index, palette="Blues_r")

plt.title("Total Grant Amount by Organization (Ontario Bridge Training Program 2012–2013)", fontsize=16)
plt.xlabel("Grant Amount (CAD)", fontsize=14)
plt.ylabel("Organization", fontsize=14)
plt.tight_layout()
plt.show()
