# HL7 v2+ IG Testing

An error resulting in the stack trace below occurs when the following both of the following CodeSystem resource files are present:

- testv2ig/input/sourceOfTruth//v2-cs-complex-data-types.json
- testv2ig/input/sourceOfTruth//v2-cs-primitive-data-types.json

If only one of these CodeSystem files (or neither) is present, the error does not occur.

Why?

```
Exception generating resource /ig/input/sourceOfTruth/v2-vs-data-types::ValueSet/v2-vs-data-types: Invalid char ([) found at index (23) in sheet name 'Include from CodeSystem[http: 2' (00:02.723 / 00:14.612, 963Mb)
java.lang.IllegalArgumentException: Invalid char ([) found at index (23) in sheet name 'Include from CodeSystem[http: 2'
	at org.apache.poi.ss.util.WorkbookUtil.validateSheetName(WorkbookUtil.java:150)
	at org.apache.poi.xssf.usermodel.XSSFWorkbook.createSheet(XSSFWorkbook.java:909)
	at org.hl7.fhir.r5.renderers.spreadsheets.SpreadsheetGenerator.makeSheet(SpreadsheetGenerator.java:111)
	at org.hl7.fhir.r5.renderers.spreadsheets.ValueSetSpreadsheetGenerator.genIncludeSystem(ValueSetSpreadsheetGenerator.java:117)
	at org.hl7.fhir.r5.renderers.spreadsheets.ValueSetSpreadsheetGenerator.genInclude(ValueSetSpreadsheetGenerator.java:87)
	at org.hl7.fhir.r5.renderers.spreadsheets.ValueSetSpreadsheetGenerator.renderValueSet(ValueSetSpreadsheetGenerator.java:40)
	at org.hl7.fhir.igtools.publisher.Publisher.generateOutputsValueSet(Publisher.java:11774)
	at org.hl7.fhir.igtools.publisher.Publisher.generateResourceHtml(Publisher.java:10785)
	at org.hl7.fhir.igtools.publisher.Publisher.generateHtmlOutputs(Publisher.java:10532)
	at org.hl7.fhir.igtools.publisher.Publisher.generate(Publisher.java:7584)
	at org.hl7.fhir.igtools.publisher.Publisher.createIg(Publisher.java:1194)
	at org.hl7.fhir.igtools.publisher.Publisher.execute(Publisher.java:1016)
	at org.hl7.fhir.igtools.publisher.Publisher.main(Publisher.java:13019)
   org.apache.poi.ss.util.WorkbookUtil.validateSheetName(WorkbookUtil.java:150)                      (00:00.001 / 00:14.613, 963Mb)
   org.apache.poi.xssf.usermodel.XSSFWorkbook.createSheet(XSSFWorkbook.java:909)                     (00:00.000 / 00:14.614, 963Mb)
   org.hl7.fhir.r5.renderers.spreadsheets.SpreadsheetGenerator.makeSheet(SpreadsheetGenerator.java:111) (00:00.000 / 00:14.614, 963Mb)
   org.hl7.fhir.r5.renderers.spreadsheets.ValueSetSpreadsheetGenerator.genIncludeSystem(ValueSetSpreadsheetGenerator.java:117) (00:00.000 / 00:14.614, 963Mb)
   org.hl7.fhir.r5.renderers.spreadsheets.ValueSetSpreadsheetGenerator.genInclude(ValueSetSpreadsheetGenerator.java:87) (00:00.000 / 00:14.614, 963Mb)
   org.hl7.fhir.r5.renderers.spreadsheets.ValueSetSpreadsheetGenerator.renderValueSet(ValueSetSpreadsheetGenerator.java:40) (00:00.000 / 00:14.615, 963Mb)
   org.hl7.fhir.igtools.publisher.Publisher.generateOutputsValueSet(Publisher.java:11774)            (00:00.000 / 00:14.615, 963Mb)
   org.hl7.fhir.igtools.publisher.Publisher.generateResourceHtml(Publisher.java:10785)               (00:00.000 / 00:14.615, 963Mb)
   org.hl7.fhir.igtools.publisher.Publisher.generateHtmlOutputs(Publisher.java:10532)                (00:00.000 / 00:14.615, 963Mb)
   org.hl7.fhir.igtools.publisher.Publisher.generate(Publisher.java:7584)                            (00:00.000 / 00:14.616, 963Mb)
   org.hl7.fhir.igtools.publisher.Publisher.createIg(Publisher.java:1194)                            (00:00.000 / 00:14.616, 963Mb)
   org.hl7.fhir.igtools.publisher.Publisher.execute(Publisher.java:1016)                             (00:00.000 / 00:14.616, 963Mb)
   org.hl7.fhir.igtools.publisher.Publisher.main(Publisher.java:13019)                               (00:00.000 / 00:14.616, 963Mb)
```
