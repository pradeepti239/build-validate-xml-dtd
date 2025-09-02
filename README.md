# Library Loans XML Validation

Decision:

We must determine if library loan records are valid according to rules:  
- Each loan must have a member, a book, and a due date.  
- Each member must have ID and name.  
- Each book must have title and author.  

Signals
1. Loan records count (per file).  
2. Member ID (string format like `M001`).  
3. Member Name (non-empty text).  
4. Book Title (non-empty text).  
5. Book Author (non-empty text).  
6. Due Date (YYYY-MM-DD).  

Gaps : No check on due date being in the future.  

Risk: Wrong or incomplete data could result in books not being returned on time, lost inventory,
or incorrect fines being charged to members. If the validation rules become outdated, new fields
such as eBook loans may not be properly validated, leading to errors or missing information.

Stewardship: The data should be visible only to library staff to protect member privacy and library operations.
Active loan data is retained until the book is returned, while historical loan logs are archived for five years.

Data Domain

Primary: Library Loans  
Adjacent: [Library Catalog], [Member Accounts]  

The XML fails because Element book content does not follow the DTD, expected is book (title, author) got only book (title).
