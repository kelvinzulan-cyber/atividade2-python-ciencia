# Atividade 2 - Aplicação Prática de Python na Ciência dos Dados

**Professor:** Sergio Ricardo

**Tema:** Aplicação Prática de Python na Ciência dos Dados - Parte 2

**Alunos:**  
Kelvin Rafael Dantas Barroso  
Mayke Alves Amancio

## Descrição
# Correção da Atividade 2

Professor, segue a correção conforme o modelo enviado, incluindo os histogramas das faturas BILL_AMT1 a BILL_AMT6 e dos pagamentos PAY_AMT1 a PAY_AMT6.

```python
import pandas as pd
import matplotlib.pyplot as plt

file_path = "default_of_credit_card_clients.xls"
df = pd.read_excel(file_path)

# Histogramas das faturas
bill_columns = ['BILL_AMT1', 'BILL_AMT2', 'BILL_AMT3', 'BILL_AMT4', 'BILL_AMT5', 'BILL_AMT6']

fig, axes = plt.subplots(2, 3, figsize=(15, 10))
axes = axes.flatten()

for i, col in enumerate(bill_columns):
    axes[i].hist(df[col], bins=20, color='blue', alpha=0.7)
    axes[i].set_title(f'Histograma de {col}')
    axes[i].set_xlabel('Valor')
    axes[i].set_ylabel('Frequência')

plt.tight_layout()
plt.show()

# Histogramas dos pagamentos
payment_columns = ['PAY_AMT1', 'PAY_AMT2', 'PAY_AMT3', 'PAY_AMT4', 'PAY_AMT5', 'PAY_AMT6']

fig, axes = plt.subplots(2, 3, figsize=(15, 10))
axes = axes.flatten()

for i, col in enumerate(payment_columns):
    axes[i].hist(df[col], bins=20, color='green', alpha=0.7)
    axes[i].set_title(f'Histograma de {col}')
    axes[i].set_xlabel('Valor')
    axes[i].set_ylabel('Frequência')
    axes[i].tick_params(axis='x', rotation=45)

plt.tight_layout()
plt.show()
