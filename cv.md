# *Curriculum vitae*

## **Anton Durko**

***Contacts for communication*** 
- Anton_Durko@atlantconsult.com
- @AntonDurko
- [Linkedin](https://www.linkedin.com/in/anton-durko-405740204)

***Brief information about myself and my skills***
Hello, I'm SAP C4C/CPI/CAP Developer.
I have 2 year experience in implementation new business logic and enhancements standart functionality for this product. Strong understanding of SAP Cloud Application Studio possibility in creating new functionality in SAP C4C for implementation of business logic and knowledge enhancement basic objects, scripts, screens and designing integration with external systems. 
Have experience with design and configuration SAP CPI for mapping and integration between SAP and non-SAP systems using different formats and protocols.

\```
// Update BM Class for customer
if (this.ToCustomer.IsSet() && this.ToCustomer.CurrentCommon.IsSet() && (this.InsuranceContractType.content == "01" || this.InsuranceContractType.content == "10") && 
    this.VehicleMean.Count() > 0 && this.ContractStartDateTime.content != fromDB.ContractStartDateTime.content) {
	// Only for person
	var vehiclesByContrQry = Contract.VehicleMean.CustomerVehicleMeansQuery.QueryByElements;
	var vehiclesByContrParams = vehiclesByContrQry.CreateSelectionParams();
	// Another vehicles for this customer
	vehiclesByContrParams.Add(vehiclesByContrQry.ToParent_ToCustomer_InternalID, "I", "EQ", this.ToCustomer.InternalID);
	var vehiclesByContrResult = vehiclesByContrQry.ExecuteDataOnly(vehiclesByContrParams);
	// Get last depends on date
	var lastVehicle = vehiclesByContrResult.OrderBy(i => i.ToParent_ContractStartDateTime.content).GetLast(); 
	if (!lastVehicle.IsInitial()) {
		if (this.ContractStartDateTime.content < lastVehicle.ToParent_ContractStartDateTime.content) {
			this.ToCustomer.CurrentCommon.BMClass = lastVehicle.VehicleBMClass;
		}
		else {
			var vehicle = this.VehicleMean.GetFirst();
			if (vehicle.IsSet()) {
				this.ToCustomer.CurrentCommon.BMClass = vehicle.VehicleBMClass;
			}
		}
	}
	else {
		var vehicle = this.VehicleMean.GetFirst();
		if (vehicle.IsSet()) {
			this.ToCustomer.CurrentCommon.BMClass = vehicle.VehicleBMClass;
		}
	}
} 
\```

***Working experience***
*Position:* SAP C4C/CPI/CAP Developer
*Duration:* April 2021 - Present

***Education***
*University:* Belarusian State University of Informatics and Radioelectronics
*Specialty:* Computing machines systems and networks
*Qualification:* Software Engineer
*End year:* June 2022

***English***
B1 (Intermediate)

