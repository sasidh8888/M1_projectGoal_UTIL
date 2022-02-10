## Header .h
HEADER FILES USED IN PROJECT

#include<conio.h>

#include<stdio.h>

#include<process.h>

#include<fstream.h>

CLASS USED


## 3_impl code
## FUNCTION TO PLACE ORDER AND MAKE BILL
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
## FUNCTION TO READ ALL RECORDS FROM FILE
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
## FUNCTION TO MODIFY RECORD OF FILE
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

## FUNCTION TO READ SPECIFIC RECORD FROM FILE
void display_sp(int n)

{
int flag=0;

fp.open("Canteen.dat",ios::in);

while(fp.read((char*)&pr,sizeof(product)))

{

if(pr.retpno()==n)

{

clrscr();

pr.show_product();

flag=1;
}

fp.close();

if(flag==0)

cout<<"\n\nSorry!!! Record not exist";

getch();

}

## FUNCTION TO DELETE A PRODUCT

void delete_product()

{

int no;

clrscr();

cout<<"\n\n\n\nDELETE PRODUCT";
cout<<"\n\nPlease Enter The product no. of The Product You Want To

Delete:";

cin>>no;

fp.open("Canteen.dat",ios::inlios::out);

fstream fp2;

fp2.open("Temp.dat",ios::out);

fp.seekg (0,ios::beg);

while(fp.read((char*)&pr,sizeof(product)))

{

if(pr.retpno()!=no)

{

fp2.write((char*)&pr,sizeof(product));
}

}

fp2.close();

fp.close();

remove("Canteen.dat");

rename("Temp.dat","Canteen.dat");

cout<<"\n\n\tRecord Deleted Successfully...";

getch();

## FUNCTION TO DISPLAY THE PRICE LIST

void menu()

{

clrscr();

4

fp.open("Canteen.dat",ios::in);

if(!fp)

{
cout<<"ERROR!!! FILE COULD NOT BE OPEN\n\n\n First Add A

Product";

cout<<"\n\n\n Program is closing....";

getch();

exit(0);
}

cout<<"\n\n\t\tProduct MENU\n\n";

cout<<"===========

==\n";

cout<<"P.NO.\t\tNAME\t\tPRICE\n";

cout<<"======

==\n";

while(fp.read((char*)&pr,sizeof(product)))

{
cout<<pr.retpno()<<"\t\t"<<pr.retname()<<"\t\t"<<pr.retprice()<<endl;

}

fp.close();

}

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

fp.read((char*)&pr,sizeof(product));

}

fp.close();
}
}

cout<<"\n\n\t\t\t\t\tTOTAL = "<<total;

cout<<"\n\n\n\nTHANK YOU FOR PLACING ORDER";

getch();

}
