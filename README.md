# Phylogeny-of-Pigeons
Phylogeography of Pigeons in Pakistan

Author List: Muhammad Tayyub, Shazad Ali, Gilbert Tom, Shym

Pigeon phylogeography ang phylogeny in pakistan and reported from different regions of the world.

import pandas as pd

# File name
file_path = "Columba_Metadata.xlsx"

# Read Excel file (first sheet by default)
df = pd.read_excel(file_path, engine="openpyxl")

# Show first 5 rows
print(df.head())

pip install biopython
from Bio import SeqIO

file_path = "all_sequences.fsa"

# Parse all sequences
sequences = list(SeqIO.parse(file_path, "fasta"))

# Print basic info
print(f"Total sequences: {len(sequences)}\n")

for record in sequences[:5]:  # show first 5 only
    print(f"ID: {record.id}")
    print(f"Description: {record.description}")
    print(f"Sequence length: {len(record.seq)}\n")
import pandas as pd
from Bio import SeqIO

file_path = "all_sequences.fsa"

data = []
for record in SeqIO.parse(file_path, "fasta"):
    data.append({
        "ID": record.id,
        "Description": record.description,
        "Sequence": str(record.seq),
        "Length": len(record.seq)
    })

df = pd.DataFrame(data)
df.to_csv("all_sequences.csv", index=False)

print("✅ Sequences exported to all_sequences.csv")
import pandas as pd
from Bio import SeqIO

file_path = "all_sequences.fsa"

data = []
for record in SeqIO.parse(file_path, "fasta"):
    data.append({
        "ID": record.id,
        "Description": record.description,
        "Sequence": str(record.seq),
        "Length": len(record.seq)
    })

df = pd.DataFrame(data)
df.to_csv("all_sequences.csv", index=False)

print("✅ Sequences exported to all_sequences.csv")
