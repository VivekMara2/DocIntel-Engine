# DocIntel Engine

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE.md)
[![Author: Vivek Reddy Mara](https://img.shields.io/badge/Author-Vivek%20Reddy%20Mara-orange.svg)](AUTHOR.md)

Welcome to **DocIntel Engine**! This project provides comprehensive code samples, tutorials, and post-processing tools for extracting structured data, text, tables, and document structures using the **Azure AI Document Intelligence SDK** across multiple programming languages.

---

## 👤 Project Owner & Maintainer

* **Author:** **Vivek Reddy Mara**
* **Email:** [vivekr5345@gmail.com](mailto:Vivekr5345@gmail.com)
* **Phone:** (618) 803-9485
* **LinkedIn:** [linkedin.com/in/vivek-r-7496371ab](https://www.linkedin.com/in/vivek-r-7496371ab)
* **Author Details:** See [AUTHOR.md](AUTHOR.md)

---

## 🚀 Supported SDK Languages

Code samples are organized by language SDK version (v4.0 GA & v3.1 GA):

| Language | Sample Directory | API Version |
| :--- | :--- | :--- |
| 🐍 **Python** | [Python(v4.0)](Python(v4.0)) | v4.0 GA (2024-11-30) / v3.1 |
| 🔷 **.NET (C#)** | [.NET(v4.0)](.NET(v4.0)) | v4.0 GA / v3.1 |
| ☕ **Java** | [Java(v4.0)](Java(v4.0)) | v4.0 GA / v3.1 |
| 🟨 **JavaScript / Node.js** | [JavaScript(v4.0)](JavaScript(v4.0)) | v4.0 GA / v3.1 |

---

## 📑 Table of Contents

- [Features & Capabilities](#-features--capabilities)
- [Prerequisites](#-prerequisites)
- [Quick Start & Setup](#-quick-start--setup)
- [Sample Catalog](#-sample-catalog)
  - [Common Models](#common-models)
  - [Prebuilt Models](#prebuilt-models)
  - [Custom Models & Classifiers](#custom-models--classifiers)
  - [Add-on Capabilities](#add-on-capabilities)
  - [RAG & Generative AI Integration](#retrieval-augmented-generation-rag-samples)
  - [Pre/Post-Processing Utilities](#prepost-processing-samples)
- [Author & License](#-author--license)

---

## 🌟 Features & Capabilities

Azure AI Document Intelligence uses machine learning to automate data extraction from structured and unstructured documents:

* 📄 **Document Analysis Models**: Extract text, handwriting, layout tables, selection marks, and semantic document structures using **Read** and **Layout** models.
* 💳 **Prebuilt Business Models**: Instant extraction for Invoices, Receipts, Identity Documents, Contracts, W-2 Forms, Mortgage Documents (1003, 1004, 1005, 1008), Bank Statements, and Pay Stubs.
* 🎯 **Custom Extractor & Classifier Models**: Build custom neural and template models or classify document batches.
* 🔍 **Add-on Capabilities**: Extract formulas, barcodes, font properties, high-resolution document elements, and custom query fields.
* 🧠 **RAG (Retrieval Augmented Generation) Integration**: Combine Document Intelligence with **LangChain**, **Azure OpenAI GPT-4V**, and **Azure AI Search** for semantic chunking and visual figure analysis.

---

## ⚡ Prerequisites

1. **Azure Subscription**: [Create one for free](https://azure.microsoft.com/free/).
2. **Azure AI Document Intelligence Resource**: [Create a Document Intelligence resource](https://learn.microsoft.com/azure/ai-services/document-intelligence/create-document-intelligence-resource) to get your **Endpoint** and **API Key**.
3. **Language Runtime**:
   - Python 3.8+ (for Python samples)
   - .NET SDK 6.0+ (for C# samples)
   - JDK 11+ (for Java samples)
   - Node.js 18+ (for JavaScript samples)

---

## 🛠️ Quick Start & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/VivekMara2/DocIntel-Engine.git
cd DocIntel-Engine
```

### 2. Python Setup
```bash
pip install azure-ai-documentintelligence azure-identity
```

### 3. Set Environment Variables
Set your Azure resource endpoint and API key:

**Windows PowerShell:**
```powershell
$env:DOCUMENTINTELLIGENCE_ENDPOINT="https://<your-resource-name>.cognitiveservices.azure.com/"
$env:DOCUMENTINTELLIGENCE_API_KEY="<your-api-key>"
```

**Linux / macOS:**
```bash
export DOCUMENTINTELLIGENCE_ENDPOINT="https://<your-resource-name>.cognitiveservices.azure.com/"
export DOCUMENTINTELLIGENCE_API_KEY="<your-api-key>"
```

---


### Common Models

| Model | Sample File | Description |
| :--- | :--- | :--- |
| **Read** | [sample_analyze_read.py](Python(v4.0)/Read_model/sample_analyze_read.py) | Extract printed and handwritten text from documents. |
| **Layout** | [sample_analyze_layout.py](Python(v4.0)/Layout_model/sample_analyze_layout.py) | Extract text, selection marks, tables, and section headings. |

### Prebuilt Models

* [sample_analyze_invoices.py](Python(v4.0)/Prebuilt_model/sample_analyze_invoices.py) — Extract customer, vendor, and line item details from invoices.
* [sample_analyze_receipts.py](Python(v4.0)/Prebuilt_model/sample_analyze_receipts.py) — Extract sales transaction details from receipts.
* [sample_analyze_identity_documents.py](Python(v4.0)/Prebuilt_model/sample_analyze_identity_documents.py) — Extract passport and driver's license details.
* [sample_analyze_contracts.py](Python(v4.0)/Prebuilt_model/sample_analyze_contracts.py) — Extract agreements, dates, and party details.
* [sample_analyze_tax_us_w2.py](Python(v4.0)/Prebuilt_model/sample_analyze_tax_us_w2.py) — Extract taxable compensation details from US W-2 forms.
* [sample_analyze_bank_statement.py](Python(v4.0)/Prebuilt_model/sample_analyze_bank_statement.py) — Extract account details and transactions from bank statements.
* [sample_analyze_pay_stub.py](Python(v4.0)/Prebuilt_model/sample_analyze_pay_stub.py) — Extract payment, tax, and employee details from pay stubs.

### Custom Models & Classifiers

* [sample_analyze_custom_documents.py](Python(v4.0)/Custom_model/sample_analyze_custom_documents.py) — Extract data using custom-trained models.
* [sample_classify_document.py](Python(v4.0)/Custom_model/sample_classify_document.py) — Classify multi-page documents into designated classes.
* [sample_compose_model.py](Python(v4.0)/Custom_model/sample_compose_model.py) — Aggregate multiple custom models into a single composed model.
* [sample_copy_model_to.py](Python(v4.0)/Custom_model/sample_copy_model_to.py) — Copy trained custom models across Azure resources.
* [sample_manage_models.py](Python(v4.0)/Custom_model/sample_manage_models.py) — List, inspect, and delete custom models.

### Add-on Capabilities

* [sample_analyze_addon_barcodes.py](Python(v4.0)/Add-on_capabilities/sample_analyze_addon_barcodes.py) — Extract barcode properties.
* [sample_analyze_addon_formulas.py](Python(v4.0)/Add-on_capabilities/sample_analyze_addon_formulas.py) — Extract inline and display formulas (LaTeX).
* [sample_analyze_addon_fonts.py](Python(v4.0)/Add-on_capabilities/sample_analyze_addon_fonts.py) — Extract font styles, weights, and text colors.
* [sample_analyze_addon_highres.py](Python(v4.0)/Add-on_capabilities/sample_analyze_addon_highres.py) — Analyze high-resolution documents.
* [sample_analyze_addon_languages.py](Python(v4.0)/Add-on_capabilities/sample_analyze_addon_languages.py) — Detect languages in document text.
* [sample_analyze_addon_query_fields.py](Python(v4.0)/Add-on_capabilities/sample_analyze_addon_query_fields.py) — Query specific custom fields during extraction.

### Retrieval Augmented Generation (RAG) Samples

* [sample_rag_langchain.ipynb](Python(v4.0)/Retrieval_Augmented_Generation_(RAG)_samples/sample_rag_langchain.ipynb) — Use Document Intelligence for semantic Markdown chunking with LangChain & Azure AI Search.
* [sample_figure_understanding.ipynb](Python(v4.0)/Retrieval_Augmented_Generation_(RAG)_samples/sample_figure_understanding.ipynb) — Crop embedded figures and pass them to Azure OpenAI GPT-4V for visual understanding.
* [sample_identify_and_merge_cross_page_tables.py](Python(v4.0)/Retrieval_Augmented_Generation_(RAG)_samples/sample_identify_and_merge_cross_page_tables.py) — Post-process and merge multi-page tables across page boundaries.

### Pre/Post-Processing Samples

* [sample_disambiguate_similar_characters.py](Python(v4.0)/Pre_or_post_processing_samples/sample_disambiguate_similar_characters.py) — Resolve character ambiguity (e.g. `O` vs `0`, `I` vs `1`) using custom post-processing rules.
* [sample_identify_cross_page_tables.py](Python(v4.0)/Pre_or_post_processing_samples/sample_identify_cross_page_tables.py) — Identify multi-page table continuations.

---

## 📜 Author & License

* **Author:** **Vivek Reddy Mara** ([Vivekr5345@gmail.com](mailto:Vivekr5345@gmail.com))
* **License:** This project is licensed under the [MIT License](LICENSE.md) — Copyright (c) **Vivek Reddy Mara**.
