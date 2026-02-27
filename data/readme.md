# About Dataset

```
"This dataset contains high-quality synthetic transaction records created specifically for fraud detection research and machine learning applications. It is suitable for building, training, and evaluating classification models such as XGBoost, Random Forest, and Logistic Regression. The dataset captures realistic transaction patterns, including both legitimate and fraudulent activities, making it ideal for benchmarking algorithms, feature engineering, and model validation. Provided in CSV format under a CC0 1.0 Public Domain license, it can be freely used for academic research, teaching, experimentation, and commercial projects without restrictions."
```

## Source

-   This dataset is fully synthetic and was generated for research and educational purposes. No real customer or transaction data was used, ensuring privacy and compliance with data protection regulations

-   The dataset was created using algorithmic simulation of financial transactions to mimic realistic patterns of legitimate and fraudulent activities. Variables such as transaction amounts, merchant categories, locations, payment methods, and fraud occurrences were generated based on probabilistic models and domain knowledge of typical fraud behavior. This approach ensures a balanced and high-quality dataset suitable for training and testing machine learning models

## Variables

```python
RangeIndex: 50000 entries, 0 to 49999
Data columns (total 21 columns):
 #   Column                        Non-Null Count  Dtype  
---  ------                        --------------  -----  
 0   Transaction_ID                50000 non-null  str    
 1   User_ID                       50000 non-null  str    
 2   Transaction_Amount            50000 non-null  float64
 3   Transaction_Type              50000 non-null  str    
 4   Timestamp                     50000 non-null  str    
 5   Account_Balance               50000 non-null  float64
 6   Device_Type                   50000 non-null  str    
 7   Location                      50000 non-null  str    
 8   Merchant_Category             50000 non-null  str    
 9   IP_Address_Flag               50000 non-null  int64  
 10  Previous_Fraudulent_Activity  50000 non-null  int64  
 11  Daily_Transaction_Count       50000 non-null  int64  
 12  Avg_Transaction_Amount_7d     50000 non-null  float64
 13  Failed_Transaction_Count_7d   50000 non-null  int64  
 14  Card_Type                     50000 non-null  str    
 15  Card_Age                      50000 non-null  int64  
 16  Transaction_Distance          50000 non-null  float64
 17  Authentication_Method         50000 non-null  str    
 18  Risk_Score                    50000 non-null  float64
 19  Is_Weekend                    50000 non-null  int64  
 20  Fraud_Label                   50000 non-null  int64  
```

### Transaction_Type vs Device_Type

1. **Transaction_Type (Natura Tranzactiei)**
 
-   ATM Withdrawal: Scoatere de numerar

-   POS (Point of Sale): Plata la un terminal (comerciant)

-   Online: Tranzactie pe internet (e-commerce)

-   Bank Transfer: Transfer direct intre conturi

2. **Device_Type**

-   dispozitivul digital folosit de utilizator pentru a autoriza, initia sau prin care a fost procesata tranzactia in sistemul bancii

### De ce apar aceste anomalii cum ar "ATM Withdrawal + Tablet/Mobile" sau "POS + Laptop" ??? Avem urmatoarele posibile cauze:

-   **Cardless Withdrawal**: Multe banci permit acum generarea unui cod de retragere direct din aplicatia bancara de pe tableta sau telefon. Te duci la ATM, introduci codul generat pe tableta si primesti banii. Sistemul inregistreaza tranzactia ca "ATM", dar dispozitivul care a comandat-o este tableta

-   **Virtual Terminal / SoftPOS**: Multi comercianti mici folosesc laptopuri sau tablete drept case de marcat (ex: Shopify POS). Daca platesti cu cardul la un festival unde vanzatorul are un cititor conectat la un laptop, tranzactia este de tip POS, dar creierul este laptopul

-   **Zgomot în Datele Sintetice**`: Fiind un set de date sintetic, uneori algoritmii de generare creeaza aceste combinatii pentru a simula zgomotul (noise) din datele reale sau pentru a testa daca modelul de Machine Learning se lasa pacalit de corelatii absurde

Astea ar fi 3 posibile cauze destul de plauzibile care ar explica de ce avem unele combinatii ciudate cum ar fi plata la POS facuta cu un Laptop

