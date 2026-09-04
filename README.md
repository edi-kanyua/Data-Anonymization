# Bank Customer Data Anonymization

## Project Overview

This project demonstrates a practical approach to protecting sensitive customer information through data anonymization and privacy-preserving transformations.

The project uses Python and Pandas to transform a customer dataset containing personally identifiable information (PII), financial information, demographic attributes, and 
other potentially sensitive fields.

The objective is to reduce privacy and re-identification risks while preserving enough analytical utility for legitimate data analysis.

## Objectives

*   Identify direct identifiers, quasi-identifiers, and sensitive attributes within customer data.
*   Apply appropriate anonymization techniques to different types of sensitive information.
*   Preserve useful relationships and analytical characteristics where possible.

## Anonymization Techniques

| Data Attribute       | Technique                |
| -------------------- | ------------------------ |
| Customer ID          | Suppression              |
| Current location     | Suppression              |
| Email                | Masking                  |
| Username             | Masking                  |
| Credit card number   | Masking                  |
| Security code        | Masking                  |
| Name                 | Pseudonymization         |
| Address              | Pseudonymization         |
| Residence            | Pseudonymization         |
| Birthdate            | Consistent date shifting |
| Registration date    | Consistent date shifting |
| Age                  | Generalization           |
| Salary               | Generalization           |
| Credit card provider | Tokenization             |
| Credit card expiry   | Tokenization             |

## Methodology

The project follows four main steps

1. The dataset is inspected and its attributes are classified according to their privacy sensitivity.

2. Columns are categorized as direct identifiers, quasi-identifiers, sensitive attributes, or other potentially identifying information.

3. Appropriate privacy-preserving techniques are applied to each category of data.

4. The transformed dataset is evaluated to confirm that the intended transformations were successfully applied and that important data structure was preserved.

## Key Privacy Considerations

Different techniques provide different levels of protection.

Direct identifiers are removed or masked, while other attributes are generalized or transformed to reduce their ability to identify individuals.

Consistent date shifting preserves relationships between dates while changing their original values. Pseudonymization and tokenization maintain some analytical relationships but 
may remain linkable depending on how the transformation keys are managed.

## Privacy–Utility Trade-off

Anonymization involves balancing privacy protection against analytical usefulness.

Removing or heavily transforming information can improve privacy but may reduce the value of the dataset for analysis. This project therefore retains useful analytical structure where possible,
including demographic groups, salary bands, employment information, and transformed temporal information.

The goal is to reduce exposure of sensitive information while retaining sufficient structure for meaningful analysis.

## Technologies

* Python
* Pandas
* NumPy
* Faker
* Matplotlib
* Seaborn
* Jupyter Notebook / Google Colab

## Project Structure

bank-customer-data-anonymization/
│
├── README.md
├── requirements.txt
├── .gitignore
├── data_anonymization.ipynb
│
└── data/
    └── Raw dataset excluded from version control


## Data Privacy Notice

The raw customer dataset is excluded from version control using `.gitignore`.

Sensitive or personally identifiable customer information have not been uploaded to the public repo. The notebook and repo
uses synthetic, appropriately anonymized, or otherwise authorized data.

## Limitations

Anonymization does not automatically guarantee complete protection against re-identification.

Some transformed attributes may retain relationships that could potentially be exploited when combined with external information. 
Pseudonymization and tokenization may also preserve linkability depending on the implementation.

The effectiveness of anonymization should therefore be assessed in the context of the intended use, available external information, and potential threat models.

## Conclusion

This project demonstrates how multiple anonymization techniques can be combined to protect sensitive customer information while preserving 
useful analytical structure.

The project emphasizes that effective data privacy is not simply about removing information. It requires understanding the privacy 
risks associated with different attributes, selecting appropriate transformations, validating their implementation, and considering the resulting privacy–utility trade-off.
