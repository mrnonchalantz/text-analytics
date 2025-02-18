import PyPDF2

## _Read the PDF file_

with open('Business_Proposal.pdf', 'rb') as file:
reader = PyPDF2.PdfReader(file)

## _Ensure the document has at least 2 pages_

    if len(reader.pages) >= 2:
        text = reader.pages[1].extract_text()  # Page index starts from 0
    else:
        text = "Error: The document does not have a second page."

## _Print the extracted text_

print("Extracted Text from Page 2:\n", text)

## _Store the extracted text in a file_

with open('business_proposal_page_2.txt', 'w', encoding='utf-8') as output:
output.write(text)

## _Result_

Extracted Text from Page 2:
AUTHORS:  
Amy Baker, Finance Chair, x345, abaker@ourcompany.com  
Chris Donaldson, Accounting Dir., x621, cdonaldson@ourcompany.com  
Erin Freeman, Sr. VP, x879, efreeman@ourcompany.com
