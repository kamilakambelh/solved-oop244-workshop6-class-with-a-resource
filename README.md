Download Link: https://assignmentchef.com/product/solved-oop244-workshop6-class-with-a-resource
<br>
Upon successful completion of this workshop, you will have demonstrated the abilities to:

<ul>

 <li>define a copy constructor</li>

 <li>define an assignment operator</li>

 <li>define a destructor</li>

 <li>avoid duplication in coding these special member functions</li>

 <li>describe what you have learned in completing this workshop</li>

</ul>

<strong>IN</strong><strong>–</strong><strong>LAB </strong><strong>: </strong>

Design a class named Contact, in namespace sict.  This class holds information about a person and their phone numbers.  The maximum number of characters in the person’s name is stored in an unmodifiable variable named MAX_CHAR. The type Contact contains the following information:

an array of characters of size MAX_CHAR (excluding the null byte ‘ ’) that holds the name of the contact;

a pointer to a <strong>dynamically allocated</strong> array of phone numbers.  A valid phone number has one to two digits for the country code (cannot be zero), <strong>exactly</strong> three digits for the area code (cannot start with zero) and <strong>exactly</strong> seven digits for the number (cannot start with zero);

the number of phone numbers currently stored in the <strong>dynamically allocated</strong> array;

Your type exposes the following public member functions:

<strong>default constructor</strong> (a constructor with no parameters): this constructor sets the current object to a safe empty state;

<strong>constructor with 3 parameters</strong>: This constructor receives the address of an unmodifiable C-style string that holds the name of the contact, the address of an unmodifiable array of phone numbers and the number of phone numbers stored in the array. This constructor allocates enough memory dynamically to hold <strong>only the valid</strong> phone numbers from the array received and copies the valid numbers into the allocated array;

<strong>destructor</strong>: the destructor deallocates any memory that has been allocated dynamically;

bool isEmpty() const: a query that returns false if the current object has valid data; true if the object is in a safe empty state;

void display() const: a query that inserts into the standard output stream the data stored by the object applying the following format:

If the object is in a safe empty state, this function displays the following message:

Empty contact!&lt;ENDL&gt;

If the object is not in a safe empty state, this function displays the following message:

CONTACT_NAME&lt;ENDL&gt;

(+COUNTRY_CODE) AREA_CODE NNN-NNNN&lt;ENDL&gt;

(+COUNTRY_CODE) AREA_CODE NNN-NNNN&lt;ENDL&gt;

<ul>

 <li>••</li>

</ul>

(+COUNTRY_CODE) AREA_CODE NNN-NNNN&lt;ENDL&gt;

Introduce as many private member functions as necessary to avoid any duplication of code in your Contact module.  Store your class definition in a header file named Contact.h and your function definitions in an implementation file named Contact.cpp.  Avoiding duplication will reduce the time that you will need to spend on the at home section.

Using the sample implementation of the w6_in_lab.cpp main module listed below, test your code and make sure that it works on Visual Studio.  The expected output from your program is listed below this source code. The output of your program should match <strong>exactly</strong> the expected one.

<strong>I</strong><strong>N</strong><strong>-L</strong><strong>AB </strong><strong>M</strong><strong>AIN </strong><strong>M</strong><strong>ODULE</strong>

<table width="628">

 <tbody>

  <tr>

   <td width="628">#include &lt;iostream&gt;#include “Contact.h”using namespace std; using namespace sict; int main(){cout &lt;&lt; “—————————————-” &lt;&lt; endl;cout &lt;&lt; “Maximum no of characters in a name: “&lt;&lt; sict::MAX_CHAR &lt;&lt; endl;cout &lt;&lt; “—————————————-” &lt;&lt; endl;     cout &lt;&lt; “Testing the default constructor!” &lt;&lt; endl;     cout &lt;&lt; “—————————————-” &lt;&lt; endl;     sict::Contact empty; // sict:: intentional     empty.display();cout &lt;&lt; “—————————————-” &lt;&lt; endl &lt;&lt; endl; cout &lt;&lt; “—————————————-” &lt;&lt; endl;     cout &lt;&lt; “Testing an invalid contact!” &lt;&lt; endl;cout &lt;&lt; “—————————————-” &lt;&lt; endl;Contact bad(nullptr, nullptr, 0);     bad.display();Contact alsoBad(“”, nullptr, 0);     alsoBad.display();cout &lt;&lt; “—————————————-” &lt;&lt; endl &lt;&lt; endl;cout &lt;&lt; “—————————————-” &lt;&lt; endl;     cout &lt;&lt; “Testing the constructor with parameters!” &lt;&lt; endl;     cout &lt;&lt; “—————————————-” &lt;&lt; endl;</td>

  </tr>

  <tr>

   <td width="628">    Contact temp(“A contact with a very looooong name!”, nullptr, 0);     temp.display();cout &lt;&lt; “—————————————-” &lt;&lt; endl &lt;&lt; endl; cout &lt;&lt; “—————————————-” &lt;&lt; endl;     cout &lt;&lt; “Testing a valid contact!” &lt;&lt; endl;cout &lt;&lt; “—————————————-” &lt;&lt; endl;long long phoneNumbers[] = { 1416123456LL, 14161234567LL, 1416234567890LL,14162345678LL, -1LL, 124163456789LL,14161230002LL };Contact someContact(“John Doe”, phoneNumbers, 7);     someContact.display();cout &lt;&lt; “—————————————-” &lt;&lt; endl &lt;&lt; endl; return 0;}</td>

  </tr>

 </tbody>

</table>

<strong>I</strong><strong>N</strong><strong>-L</strong><strong>AB </strong><strong>O</strong><strong>UTPUT</strong>

—————————————-

Maximum no of characters in a name: 20

—————————————-

Testing the default constructor! —————————————-

Empty contact!

—————————————-




—————————————-

Testing an invalid contact!

—————————————-

Empty contact!

Empty contact!

—————————————-




—————————————- Testing the constructor with parameters!

—————————————-

A contact with a ver

—————————————-




—————————————-

Testing a valid contact!

—————————————-

John Doe

(+1) 416 123-4567

(+1) 416 234-5678

(+12) 416 345-6789

(+1) 416 123-0002

—————————————-

<strong>I</strong><strong>N</strong><strong>-L</strong><strong>AB </strong><strong>S</strong><strong>UBMISSION</strong>

To test and demonstrate execution of your program use the same data as the output example above.

If not on matrix already, upload Contact.h, Contact.cpp and w6_in_lab.cpp to your matrix account. Compile and run your code and make sure everything works properly.

Then, run the following command from your account (use your professor’s Seneca userid to replace profname.proflastname, and your section ID to replace XXX, i.e., SAA, SBB, etc.):

<h2>~profname.proflastname/submit 244XXX_w6_lab&lt;<sub>ENTER&gt;</sub></h2>

and follow the instructions generated by the command and your program.

<table width="642">

 <tbody>

  <tr>

   <td width="642"><strong>I</strong><strong>MPORTANT</strong>: Please note that a successful submission does not guarantee full creditfor this workshop. If your professor is not satisfied with your implementation, your professor may ask you to resubmit. Resubmissions will attract a penalty.</td>

  </tr>

 </tbody>

</table>




<strong>A</strong><strong>T</strong><strong>-H</strong><strong>OME</strong>

For the <em>at-home</em> part, copy the Contact module that you created for your <em>inlab</em> submission. Declare the following additional member functions in the class definition and implement them in the .cpp file:

<strong>copy constructor</strong>: this constructor receives an unmodifiable reference to a

Contact object copies that object into the newly created instance; <strong>copy assignment operator</strong>: this operator receives an unmodifiable reference to a Contact object and copies the content of that object into the existing current object and returns a reference to the current object, as updated.

<strong>an overloaded += operator</strong>: this operator receives a new phone number as its parameter, validates the number received and, if valid, resizes the phone number array to hold all the existing numbers plus the received one and finally adds this new number to the array. If the number is not valid, this operator retains the original array and does not add the number.  In either case, this operator returns a reference to the current object.

<strong>N</strong><strong>OTE</strong>: When you implement the copy assignment operator, make sure that the Contact instance is not being set to itself.

Using the sample implementation of the w6_at_home.cpp main module listed below, test your code and make sure that it works on Visual Studio. The expected output from your program is listed below this source code. The output of your program should match <strong>exactly</strong> the expected one.

<strong>A</strong><strong>T</strong><strong>-H</strong><strong>OME </strong><strong>M</strong><strong>AIN </strong><strong>M</strong><strong>ODULE</strong>

<table width="628">

 <tbody>

  <tr>

   <td width="628">#include &lt;iostream&gt;#include “Contact.h”using namespace std; using namespace sict; int main() {cout &lt;&lt; “—————————————-” &lt;&lt; endl;cout &lt;&lt; “Maximum no of characters in a name: “&lt;&lt; sict::MAX_CHAR &lt;&lt; endl;     sict::Contact theContact(“John Doe”, nullptr, 0); // sict:: intentional     theContact.display();     theContact += 14161234567LL;     theContact += 14162345678LL;</td>

  </tr>

  <tr>

   <td width="628">    theContact += 14163456789LL;     theContact += 114164567890LL;     theContact.display(); cout &lt;&lt; endl &lt;&lt; “Testing! Please wait:” &lt;&lt; endl; for (int i = 1; i &lt;= 5000000; i++){Contact temp = theContact;         theContact = temp;         theContact = theContact;         if (!(i % 10000))             cout &lt;&lt; “.”;         if (!(i % 500000))             cout &lt;&lt; endl;}cout &lt;&lt; endl;theContact.display(); theContact = Contact(“”, nullptr, 0);  theContact += 14161230002LL;  theContact.display(); return 0;}</td>

  </tr>

 </tbody>

</table>

<strong>A</strong><strong>T</strong><strong>-H</strong><strong>OME </strong><strong>E</strong><strong>XPECTED </strong><strong>O</strong><strong>UTPUT</strong>

<table width="628">

 <tbody>

  <tr>

   <td width="628">—————————————-Maximum no of characters in a name: 20-John DoeJohn Doe(+1) 416 123-4567(+1) 416 234-5678(+1) 416 345-6789(+11) 416 456-7890 Testing! Please wait:…………………………………………..…………………………………………..…………………………………………..…………………………………………..…………………………………………..…………………………………………..…………………………………………..…………………………………………..………………………………………….. …………………………………………..John Doe(+1) 416 123-4567 (+1) 416 234-5678(+1) 416 345-6789(+11) 416 456-7890 Empty contact!</td>

  </tr>

 </tbody>

</table>

<strong>REFLECTION </strong><strong>(40%) </strong>

Study your final solution, reread the related parts of the course notes, and make sure that you have understood the concepts covered by this workshop. <strong>This should take no less than 30 minutes of your time.</strong>

Create a file named reflect.txt that contains your <strong>detailed description of the topics that you have learned </strong>in completing this workshop and mention any issues that caused you difficulty. Include in your explanation—<strong>but do not limit it to</strong>—the following points:

<ul>

 <li>Why does the copy assignment operator check for self-assignment before doing anything else? What could go wrong if the operator doesn’t check for self-assignment?</li>

 <li>List examples of how you avoided code duplication.</li>

</ul>

<h3>QUIZ REFLECTION</h3>

Add a section to reflect.txt called Quiz X Reflection. Replace the X with the number of the last quiz that you received and list the numbers of all questions that you answered incorrectly.

Then for each incorrectly answered question write your mistake and the correct answer to that question. If you have missed the last quiz, then write all the questions and their answers.

<strong>A</strong><strong>T</strong><strong>-H</strong><strong>OME </strong><strong>S</strong><strong>UBMISSION</strong>

To submit the <em>at-home</em> section, demonstrate execution of your program with the exact output as in the example above.

Upload reflect.txt, Contact.h, Contact.cpp and w6_at_home.cpp to your matrix account. Compile and run your code and make sure everything works properly.

To submit, run the following command from your account (use your professor’s Seneca userid to replace profname.proflastname, and your section ID to replace XXX, i.e., SAA, SBB, etc.):

<h2>~profname.proflastname/submit 244XXX_w6_home&lt;<sub>ENTER&gt;</sub></h2>

and follow the instructions generated by the command and your program.

<table width="642">

 <tbody>

  <tr>

   <td width="642"><strong>I</strong><strong>MPORTANT</strong>: Please note that a successful submission does not guarantee full creditfor this workshop. If the professor is not satisfied with your implementation, your professor may ask you to resubmit. Resubmissions will attract a penalty.</td>

  </tr>

 </tbody>

</table>


