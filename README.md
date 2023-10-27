# Installing-MS-SQL-
Introduction & Objective 
- 
In this lab, we create a cloud-based virtual environment specifically designed for the installation of SQL with the primary objective of logging Windows Event Viewer data. Within this environment, we systematically capture information about both successful and failed login attempts, shedding light on the location and frequency of unauthorized access attempts by potential intruders. This tutorial provides a step-by-step guide to setting up the virtual machine, deploying SQL, and configuring the system to document and analyze login events, offering insights into security and potential threats.

Technologies, Azure Components, and Regulations Employed
- 
- Remote Desktop Protocol (RDP)
- Strucutred Query Language (SQL)
- Windows Event Viewer
- SQL Server Management Studio
- Virtual Machine
- Firewall Disabled on Windows Security

Lab Step by Step
- 
**1)** RDP (remote desktop protocol) into the VM (virtual machine) that is going to have the firewall offline. 
![1](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/a34ac16c-1978-4c2e-b40b-3aa2b4ba72c3)

![2](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/f871f79d-ab42-45f3-a190-2d8aac627ae9)

**2)** Once logged onto the VM, go into Windows Defender Firewall.

![image](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/b8bbbcce-ade9-4f2c-b977-c29a8d794bf0)

By default, the Windows Defender Firewall should look like this.


**3)** Next, click on "Windows Defender Firewall Properties" which then will take you to this page:

![4](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/ae2a0e6f-f20c-4db7-97a5-5404508799b8)

You will then turn off the Domain Profile, Private Profile, and Public Porfile in the "Firewall State".


![5](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/ae5e5d49-7129-470c-9b53-d7ec4f0ad601)

This is how it should look like once everything is disabled.

**4)** On the VM, download SQL.
![7](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/5d614338-8762-4624-866e-58025c5e3053)

**5)** Once SQL is downloaded on the VM, we will log our SQL server onto our VM.
![8](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/d01ef28a-5505-4ba1-b6a3-f9bcf579e145)

**6)** We know will insert this code into the registry editor. 
![11](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/548669c5-59b2-4cde-9f45-8e06049c99bf)


Once you copy and paste that into the registry editor, it should look like this:


![12](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/f2d7f054-b6ac-4516-b979-00d34777d53d)

**7)** Now, you will need to click on "Security" >> "Permissions" >> "Add". Once you have done all these steps, the screen look like this:  
![image](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/97e8b08d-07ed-43c1-bd21-e25a0a0d71eb)


Now, in the textbox put "NETWORK SERVICES" and click "Check Names". Once that is completed, click on "NETWORK SERVICES" and click the "Allow" boxes to allow "Full Control" and "Read". Then click apply. 


![14](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/6df82153-dc40-468b-95aa-953f350d4d2d)

**7)** Now, in the "Server Properties" in our SQL, we will check the box "Both failed and successful logons", so we can log both successful logons and failed logons.


![16](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/aee3fda9-009b-4235-ae8c-13341af1a1f4)



**8))** Now, on your Windows Event Viewer, you can now view the successful/failed logons. 
![9](https://github.com/bmpwrr/Installing-MS-SQL-/assets/144153997/7e305372-94fe-4d3c-a567-0bcdca28b75a)

Conclusion
-
In this lab, I demonstrate the procedure for monitoring both successful and unsuccessful logon attempts using the Windows Event Viewer. To access this functionality, the initial step involves establishing a connection to a virtual machine (VM). Following successful connection to the VM, the next step is to download and install SQL within the VM environment. Upon the successful installation of SQL, we proceed to enable SQL functionality within our VM. Once this configuration is complete, we are then able to effectively capture and document both successful and failed login events.













