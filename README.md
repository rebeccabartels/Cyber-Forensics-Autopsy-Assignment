## Digital Forensics Homework SOLUTION: The Case of the Little Russian Tea Room 

* Lab Environment:

	* Kali Linux
	
	* Autopsy 10.0

* Files: 

	* RussianTeaRoom.zip (560 KB) - This file contains the `Autopsy` case file and Encase image file.
	
	* menu.pdf (56.0 KB) - This file contains the Russsian Tea Room menu.
		
	* Instructor-solution.xls (15 KB) -  This file contains the answers to the assignment.
	
	* Autopsy-Image-Dump folder (268 KB) - This folder contains the image dumps for the image file locations.

---

This document contains solutions for homework **Option 2 — The Case of the Little Russian Tea Room**. For the solutions to **Option 1**, please see [Tracy-iPhone-Answers.pdf](Tracy-iPhone-Answers.pdf).

## Homework Objective

The goal of this homework assignment is to sharpen student's skills in locating and identifying data in a forensic image. This is an important skill when tasked with locating and decoding data such as executable code or a malicious document embedded in an image or network log.

## SOLUTION 

The scenario comes from the [Unicode String Searching - Russian Text](https://www.cfreds.nist.gov/utf-16-russ.html) at the [CFReDS Project at NIST](https://www.cfreds.nist.gov/).  It demonstrates UTF-16 character decoding, Endianness, and file carving.

Please see the `Instructor-solution.xls` file for the solution to the assignment.

* The complete menu is [here](menu.pdf).

* The order is Cyrillic text and then English text. Locate the **FEFF** which is the Byte Order Marker (BOM) for Big Endian. For example, ЗАКУСКИ in the image is represented by FE FF (BOM) followed by hex - 04 17 04 10 04 1A 04 23 04 21 04 1A 04 18. 

* Look for the **code point** *04 xx* Hex sequence.

* The Cyrillic text is displayed as garbage.

* The menu text is located in `text files` and in `unallocated space` in the Encase image file.  See the `Autopsy-Image-Dumps` folder.  

* The **Autopsy case file** is located in the `RussianTeaRoom.zip` file. 


## What Students Submit

* Students submit the completed **RussianTeaRoom-UTF16.xls** file.

1. Document the **complete file location** for six (6) menus in the image. 


2. Document the **menu items** in Cyrillic (e.g., бифштеке)and English (e.g,  steak) for the following menus:

	* Pancakes (Menu #3)
		
	* Meat and Fish (Menu #5)

	Include:

	* *starting location in the hex dump* (e.g., 0x00000010).
		
	* *hex string* for a menu name or menu item (e.g., `00 42 00 65 00 76 00 65 00 72 00 61 00 67 00 65 00 73`). 
		
	* *UTF-16 escape sequence* for a menu name or menu item (e.g., `\u0042\u0065\u0076\u0065\u0072\u0061\u0067\u0065\u0073`).



 
