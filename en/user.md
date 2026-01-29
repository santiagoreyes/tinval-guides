# User Guide (Role: USER)

Previous Guides: [Access Guide](./access.md)

## Validate Individual TIN

**Purpose**: Validate TINs one by one.

### Steps

1. Navigate to "Validate Individual TIN"
2. Enter the requested data:
   1. Destination country
   2. TIN number
   3. Person Type (C= Company, I = Individual)
   4. Document Type (TIN, PASS= Passport, NIDN=National Identification Number)
   5. Name
3. Click "Submit"

![Validate Individual TIN](USER_Tin_Individual_01.png)

The system processes the request and returns a success message, indicating the assigned request number, which can be used to search for it in the option: "View Validation Requests". It will normally appear among the first ones.

### Important notes

* The system will only allow selecting a destination country if it is registered in the system.
* The system will use the validation level defined between the requesting user's country and the destination country.
* The system will use the rules it finds based on the combination of Destination Country, Document Type, Person Type; otherwise it will evaluate as an invalid TIN.
* The system requires all requested fields to be completed.

## Validate TIN Batch

**Purpose**: Validate TINs in batches, included in files according to supported formats (JSON, XML, CSV).

### Steps
1. Navigate to "Validate TIN Batch"
2. Enter the requested data:
   1. Select the file containing the TINs.
3. Click "Submit"

![Validate Batches](USER_ValidarLotes_01.png)

The system processes the request and returns a success message, indicating the assigned batch number, which can be used to search for it in the option: "View Requests". It will normally appear among the first ones.

### Important notes

* The system only allows XML, JSON, CSV files
* The system only allows well-structured files; otherwise it will reject them and report the errors found.
* The system only allows uploading files with a maximum size of 1 MB.

## View Validation Requests

**Purpose**: View the results of validated TINs, whether individually or in batches, their status and details.

### Steps
1. Navigate to "View Validation Requests"
2. Click "View" for the different validated TINs, either individual or batch.

![View Requests](USER_SolicitudesValidacion_01.png)

The system will show the results of validated TINs, both individually and in batches, indicating the assigned number, which can be used to view result details in the option: "View". It will normally appear in order of request date.

### View Details of Individual Validation
1. Navigate to "View Validation Requests"
2. In the list you can see the individual validation according to the assigned validation number.
3. Clicking "View" will show Details of the validated TIN.

![View Individual Validation](USER_ValidacionIndividual_01.png)
![View Details of Individual Validation](USER_DetalleValidacionIndividual_01.png)

### View Details of Completed Batch Validation
1. Navigate to "View Validation Requests"
2. In the list you can see according to the assigned batch validation number and its Completed status.
3. Clicking "View" will show Details of the validated Batch.
4. You can see the list of TINs, each with the "View" option for details of each.
5. You can export the information in Excel format.
6. You can choose the number of TINs to be displayed per page.
7. There is a "Search" option for general search.
8. A filter is displayed with various search options accessible for more specific searches.

![View Completed Batch Validation](USER_ValidacionLoteCompletado_01.png)

### View Details of Pending Batch Validation
1. Navigate to "View Validation Requests"
2. In the list you can see according to the assigned batch validation number and its Pending status.
3. Clicking "View" will show Details of the Batch in Pending status.
4. You can see the list of TINs, each with its status and, once the Batch is Processed, there is the "View" option for details of each.
5. There is a "Search" option for general search.
6. A filter is displayed with various search options accessible for more specific searches.
7. You can export the information in Excel format.

![View Details of Pending Batch Validation](USER_ValidacionLotePendiente_01.png)

### Important notes

* The system will only allow viewing validation requests from the last 30 days.
* The system will only allow filtering information for searching validated TINs in batches.
