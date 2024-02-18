#include <iostream>
using namespace std; 


int main() {
  
  string employeeName;
  double hoursWorked;
  double hourlyRate;
  double grossPay;
  double taxRate;
  double netPay; 

  while(true){
    cout << "Welcome to my payroll system" << endl; 
    cout << "-----------------------------" << endl; 

    do{
     cout << "Enter employee name: ";
     getline(cin, employeeName);
    } while(employeeName.empty());

    do{
     cout << "Enter hours worked: ";
     cin >> hoursWorked; 
    } while(hoursWorked < 1);

    do{
     cout << "Enter hourly rate: ";
     cin >> hourlyRate;
    } while(hourlyRate < 1);

    do{
     cout << "Enter tax rate(%): ";
     cin >> taxRate; 
     cin.ignore(); 
    } while(taxRate < 1 || taxRate > 100);

    
    grossPay = hoursWorked * hourlyRate;
    netPay = grossPay - (grossPay * (taxRate / 100));

    cout << "Payroll Summary" << endl;
    cout << "-----------------------------" << endl;
    cout << "Employee Name: " << employeeName << endl;
    cout << "Hours Worked: " << hoursWorked << endl;
    cout << "Hourly Rate: " << hourlyRate << endl;
    cout << "Gross Pay: " << grossPay << endl;
    cout << "Tax Rate: " << taxRate << endl;
    cout << "Net Pay: " << netPay << endl;

    char addAnotherEmployee;

    cout << "Do you want to add another employee? (Y/any key to exit): ";
    cin >> addAnotherEmployee;
    

    if(addAnotherEmployee != 'Y' && addAnotherEmployee != 'y'){
      break;
    }
    cout << endl; 
  } 

cout << "Thank you for using my payroll system" << endl;
    
  }
