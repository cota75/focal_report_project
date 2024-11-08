# Focal Report Project

## About The Project
Quality Assurance Engineer Challenge

Before releasing changes to reports, we want to ensure that we are not introducing any regression and that the data in the reports is consistent.




## Getting Started

Python3 is required for this as well as two python libraries/utilities (csv-diff and diff-pdf-visually).



### Prerequisites
* Python3 

* csv-diff : https://pypi.org/project/csv-diff/
  ```sh
  pip install csv-diff
  ```
  
* diff-pdf-visually : https://pypi.org/project/diff-pdf-visually - This requires imageMagick and poppler to be installed
  ```sh
  Mac OS:
  brew install poppler imagemagick
  pip3 install --user diff-pdf-visually

  Windows:
  See https://pypi.org/project/diff-pdf-visually for instructions on how to install ImageMagick and pdftocairo/Poppler
  pip3 install --user diff-pdf-visually

  Linux:
  sudo apt install python3-pip imagemagick poppler-utils
  pip3 install --user diff-pdf-visually
  ```

### Instructions

1. Clone the repo
   ```sh
   git clone https://github.com/cota75/focal_report_project
   ```
3. Modify compare_reports.py with the filenames for the reports (csv/pdf) as well as the keyword used to diff the csv. 
   ```sh
   prodCSV = 'prod/gap_report_grocery_focal_superstore_101_2024-10-28_2024-10-28.csv'
   stagingCSV = 'staging/gap_report_grocery_focal_superstore_101_2024-10-28_2024-10-28.csv'
   CSV_keyword = 'Article Number'

   prodPDF = 'prod/gap_report_grocery_focal_superstore_101_2024-10-28_2024-10-28.pdf'
   stagingPDF = 'staging/gap_report_grocery_focal_superstore_101_2024-10-28_2024-10-28.pdf'
   ```
4. Save the compare_reports.py file

5. Execute the python script compare_reports.py
   ```sh
   python3 compare_reports.py
   ```

6. Optional - If you want to view the difference in the reports you can use diff-pdf
   https://vslavik.github.io/diff-pdf/
   ```sh
   diff-pdf prod.pdf staging.pdf --output-diff=diff.pdf
   ```



### Test Cases
1. Check the diff in CSV using the . If there are no differences -> Pass. If there are differences -> Fail.
2. Check the PDF image structure. If there are no differences -> Pass. If there are differences -> Fail.
3. Additional checks for test quality would be to check expected format for the values (i.e., date format), if there is a record mismatch (i.e., staging has one more row than production for the same report), also if the values for the cell match what the column expects (i.e., if the column is  "Article Name" and the value is a date or some other non-string value). 



## Contact

Richard Lau - cota75@gmail.com 

Project Link: [https://github.com/cota75/focal_report_project](https://github.com/cota75/focal_report_project)


