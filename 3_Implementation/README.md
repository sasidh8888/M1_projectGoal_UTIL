## Header .h

























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

fp.read((char*)&pr,sizeof(product));

}

fp.close();
}
}

cout<<"\n\n\t\t\t\t\tTOTAL = "<<total;

cout<<"\n\n\n\nTHANK YOU FOR PLACING ORDER";

getch();

}
