## Header .h
HEADER FILES USED IN PROJECT

#include<conio.h>

#include<stdio.h>

#include<process.h>

#include<fstream.h>

CLASS USED


## 3_impl code
FUNCTION TO PLACE ORDER AND MAKE BILL
void place order()

{

int order_arr[50],quan[50],c=0;
float amt,total=0;

char ch='Y';

menu();

cout<<"\n=======";

cout<<"\n PLACE YOUR ORDER";

cout<<"\n====\n";

do
{
cout<<"\n\nEnter The Product No. Of The Product: ";

cin>>order_arr[c];

cout<<"\nEnter The Quantity: ";

cin>>quan[c];

C++;

cout<<"\nDo You Want To Order More Products? [y/n): ";

cin>>ch;

}

while (ch=='y' || ch=='Y');

cout<<"\n\n*****BILL*\n";
for(int x=0; x<=c;x++)

(

fp.open("Canteen.dat",ios::in);

fp.read((char*)&pr,sizeof(product));

while (!fp.eof())

if(pr.retpno()==order_arr[x])
(

amt=pr.retprice()*quan[x];

cout<<"\nProduct Number: "<<order_arr[x] <<"\nProduct Name:"<<pr.retname() <<"\nQuantity: "<<quan[x] <<"\nPrice: "<<pr.retprice();

total=amt;

}

## Doxygen com code
 void display_all

clrscr();

cout<<"\n\n\n\t\tDISPLAY ALL RECORD\n\n";

fp.open("Canteen.dat",ios::in);

while(fp.read((char*)&pr,sizeof(product)))

pr.show_product():
cout<<"\n\n========\n";



getch();
}

fp.close();

getch();

}

fp.read((char*)&pr,sizeof(product));

}

fp.close();
}
}

cout<<"\n\n\t\t\t\t\tTOTAL = "<<total;

cout<<"\n\n\n\nTHANK YOU FOR PLACING ORDER";

getch();

}

## compile the code
void modify_product()
(

int no,found=0;

clrscr();

cout<<"\n\n\tMODIFY PRODUCT";

cout<<"\n\n\tPlease Enter The Product Number: ";

cin>>no;
fp.open("Canteen.dat",ios::inlios::out);

while(fp.read((char*)&pr,sizeof(product)) && found==0)

{

if(pr.retpno(==no)

{

pr.show_product();

cout<<"\nPlease Enter The New Details of Product"<<endl;

pr.add_product();

int pos=-1*sizeof(pr);

fp.seekp(pos,ios::cur);

fp.write((char*)&pr,sizeof(product));

cout<<"\n\n\t Record Updated Successfuly";
found=1;

getch();

}

}

fp.close();

if(found==0)
