
#include<iostream.h>
#include<conio.h>
#include<stdio.h>
#include<stdlib.h>
#include<bios.h>
#include<graphics.h>
#include<string.h>
#include<dos.h>
#include<fstream.h>
#include<time.h>
class Store;
class Company;
class Client;
class Sell;
int StoreFunction();
int CompanyFunction();
int ClientFunction();
int SellFunction();
int supermain();
void ShowBill();
class Store
{
 public:
	int item_ID;
	char item_name[20];
	float item_rate;
	float item_price;
	int item_qty;
	int item_exp_mm;
	int item_exp_yy;
 public:
       Store()
       {
	item_ID=0;
	strcpy(item_name,"N/A");
	item_rate=0;
	item_price=0;
	item_qty=0;
	item_exp_mm=0;
	item_exp_yy=0;
       }
       int AddNewStock();
       int ListStock();
       int UpdateStock();
       int DeleteStock();
       int CountinStock();
};
class Company
{
 private:
	int c_ID;
	char c_name[20];
	char c_person[20];
	char c_address[20];
	char c_num[10];
	float c_amt;
 public:
	Company()
	{
	 c_ID=0;
	 strcpy(c_name,"N/A");
	 strcpy(c_person,"N/A");
	 strcpy(c_address,"N/A");
	 c_amt=0;
	}
	int AddNewCompany();
	int ListCompany();
	int UpdateCompany();
	int DeleteCompany();
	int CountinCompany();
};
class Client
{

public:
	int cl_ID;
	char cl_name[20];
	char cl_address[20];
	char cl_num[10];
	float cl_amt;
public:
	Client()
       {
	cl_ID=0;
	strcpy(cl_name,"N/A");
	strcpy(cl_address,"N/A");
	cl_amt=0;
       }
       int AddNewClient();
       int ListClient();
       int UpdateClient();
       int DeleteClient();
       int CountinClient();
};
class Sell:public Store,public Client
{
 private:
	 float sellRate;
	 float sellPrice;
 public:
	int ItemSell();
	void CalcProfit();
	void BillGenerate();
};
int main()
{
int gd=DETECT,gm;
char uid[20],pass[7];
initgraph(&gd,&gm,"c://turboc3//bgi");
setbkcolor(GREEN);
rectangle(50,20,620,350);
setcolor(RED);
rectangle(220,30,360,48);
rectangle(230,143,350,160);
rectangle(230,175,350,192);
gotoxy(32,3);
cout<<"LOGIN FORM";
gotoxy(20,10);
cout<<"Username:";
gotoxy(20,12);
cout<<"Password:";
gotoxy(46,10);
cout<<"(Press enter after entering)";
gotoxy(46,12);
cout<<"(9 characters only)";
gotoxy(30,10);
gets(uid);
gotoxy(30,12);
for(int i=0;i<9;i++)
{
pass[i]=getch();
cout<<"*";
}
if((strcmp(uid,"medical")==0)&&(strcmp(pass,"Loveworld")==0))
{
gotoxy(20,20);
cout<<"Plz wait Redirecting";
for(int j=0;j<4;++j)
{
sleep(1);
cout<<".";
}
closegraph();
supermain();
}
else
{
gotoxy(20,20);
cout<<"Wrong ID or Password";
for(int j=0;j<4;++j)
{
sleep(1);
cout<<".";
exit(1);
}
}

 getch();
 return 0;
}
int Store::AddNewStock()
{
int count=0;
Store s;
clrscr();
count=CountinStock();
s.item_ID=++count;
gotoxy(35,3);
cout<<"Adding New Item To STOCK";
gotoxy(5,5);
cout<<"Item ID:";
cout<<s.item_ID;
gotoxy(5,6);
cout<<"Item Name:";
cin>>s.item_name;
gotoxy(5,7);
cout<<"Item Purchase Rate:";
cin>>s.item_rate;
gotoxy(5,8);
cout<<"Item MRP:";
cin>>s.item_price;
gotoxy(5,9);
cout<<"Item Quantity:";
cin>>s.item_qty;
gotoxy(5,10);
cout<<"Expiry Month:";
cin>>s.item_exp_mm;
gotoxy(5,11);
cout<<"Expiry Year:";
cin>>s.item_exp_yy;
ofstream file;
file.open("st.dat",ios::binary|ios::app);
file.write((char *)&s,sizeof(s));
file.close();
getch();
return 0;
}
int Store::ListStock()
{
ifstream file;
Store s;
file.open("st.dat",ios::binary);
int i=0,j=6;
clrscr();
gotoxy(35,3);
cout<<"All Available Items\n\n";
gotoxy(0,5);
cout<<"ID";
gotoxy(10,5);
cout<<"NAME";
gotoxy(30,5);
cout<<"RATE";
gotoxy(45,5);
cout<<"MRP";
gotoxy(60,5);
cout<<"QTY";
gotoxy(74,5);
cout<<"EXPIRY\n";
while(file.read((char *)&s,sizeof(s))!=NULL)
{
 gotoxy(i,j);
 cout<<s.item_ID;
 i=i+10;
 gotoxy(i,j);
 cout<<s.item_name;
 i=i+20;
 gotoxy(i,j);
 cout<<s.item_rate;
 i=i+15;
 gotoxy(i,j);
 cout<<s.item_price;
 i=i+15;
 gotoxy(i,j);
 cout<<s.item_qty;
 i=i+14;
 gotoxy(i,j);
 cout<<s.item_exp_mm<<"/"<<s.item_exp_yy<<endl;
 i=0;
 j=j+1;
}
getch();
return 0;
}
int Store::UpdateStock()
{
int id;
Store s;
clrscr();
fstream file1;
fstream file2;
file1.open("st.dat",ios::in|ios::binary);
file2.open("stemp.dat",ios::out|ios::binary);
ifstream file;
file.open("st.dat",ios::binary);
int i=0,j=6;
clrscr();
gotoxy(35,3);
cout<<"All Available Items\n\n";
gotoxy(0,5);
cout<<"ID";
gotoxy(10,5);
cout<<"NAME";
gotoxy(30,5);
cout<<"RATE";
gotoxy(45,5);
cout<<"MRP";
gotoxy(60,5);
cout<<"QTY";
gotoxy(74,5);
cout<<"EXPIRY\n";
while(file.read((char *)&s,sizeof(s))!=NULL)
{
 gotoxy(i,j);
 cout<<s.item_ID;
 i=i+10;
 gotoxy(i,j);
 cout<<s.item_name;
 i=i+20;
 gotoxy(i,j);
 cout<<s.item_rate;
 i=i+15;
 gotoxy(i,j);
 cout<<s.item_price;
 i=i+15;
 gotoxy(i,j);
 cout<<s.item_qty;
 i=i+14;
 gotoxy(i,j);
 cout<<s.item_exp_mm<<"/"<<s.item_exp_yy<<endl;
 i=0;
 j=j+1;
}
cout<<"\nEnter ID of ITEMS to update:-->";
cin>>id;
while(file1.read((char *)&s,sizeof(s))!=NULL)
{
 if(s.item_ID!=id)
  {
   file2.write((char *)&s,sizeof(s));
  }
 else
  {
   if(id==s.item_ID)
  {
	clrscr();
	gotoxy(35,3);
	cout<<"Updating Item To STOCK";
	gotoxy(5,5);
	cout<<"Item ID:";
	cout<<s.item_ID;
	gotoxy(5,6);
	cout<<"Item Name:";
	cout<<s.item_name;
	gotoxy(5,7);
	cout<<"Item New Purchase Rate:";
	cin>>s.item_rate;
	gotoxy(5,8);
	cout<<"Item New MRP:";
	cin>>s.item_price;
	gotoxy(5,9);
	cout<<"Item New Quantity:";
	cin>>s.item_qty;
	gotoxy(5,10);
	cout<<"New Expiry Month:";
	cin>>s.item_exp_mm;
	gotoxy(5,11);
	cout<<"New Expiry Year:";
	cin>>s.item_exp_yy;
	file2.write((char *)&s,sizeof(s));
	cout<<"\n!!!!Updation Successfull!!!!";
      }
     }
   }
file1.close();
file2.close();
file1.open("st.dat",ios::out|ios::binary);
file2.open("stemp.dat",ios::in|ios::binary);
while(file2.read((char *)&s,sizeof(s))!=NULL)
{
file1.write((char *)&s,sizeof(s));
}
file1.close();
file2.close();
getch();
return 0;
}
int Store::DeleteStock()
{
clrscr();
int id;
Store s;
fstream file1;
fstream file2;
file1.open("st.dat",ios::in|ios::binary);
file2.open("stemp.dat",ios::out|ios::binary);
clrscr();
ifstream file;
file.open("st.dat",ios::binary);
int i=0,j=6,ID=0;
clrscr();
gotoxy(35,3);
cout<<"All Available Items\n\n";
gotoxy(0,5);
cout<<"ID";
gotoxy(10,5);
cout<<"NAME";
gotoxy(30,5);
cout<<"RATE";
gotoxy(45,5);
cout<<"MRP";
gotoxy(60,5);
cout<<"QTY";
gotoxy(74,5);
cout<<"EXPIRY\n";
while(file.read((char *)&s,sizeof(s))!=NULL)
{
 gotoxy(i,j);
 cout<<s.item_ID;
 i=i+10;
 gotoxy(i,j);
 cout<<s.item_name;
 i=i+20;
 gotoxy(i,j);
 cout<<s.item_rate;
 i=i+15;
 gotoxy(i,j);
 cout<<s.item_price;
 i=i+15;
 gotoxy(i,j);
 cout<<s.item_qty;
 i=i+14;
 gotoxy(i,j);
 cout<<s.item_exp_mm<<"/"<<s.item_exp_yy<<endl;
 i=0;
 j=j+1;
}
cout<<"\nEnter ID to Delete:";
cin>>id;
while(file1.read((char *)&s,sizeof(s))!=NULL)
{
 if(s.item_ID<id)
  {
   file2.write((char *)&s,sizeof(s));
  }
   if(id==s.item_ID)
  {
     ID=id;
     cout<<"\n!!!!Deletion Successfull!!!!";
  }
  if(s.item_ID>id)
  {
   s.item_ID=ID++;
   file2.write((char *)&s,sizeof(s));
  }
     }
file1.close();
file2.close();
file1.open("st.dat",ios::out|ios::binary);
file2.open("stemp.dat",ios::in|ios::binary);
while(file2.read((char *)&s,sizeof(s))!=NULL)
{
file1.write((char *)&s,sizeof(s));
}
file1.close();
file2.close();
getch();
return 0;
}
int Store::CountinStock()
{
 ifstream file;
 Store s;
 int count=0;
 file.open("st.dat",ios::binary);
 if(file==NULL)
 count=0;
 while(file.read((char *)&s,sizeof(s)))
 {
  count++;
 }
 file.close();
 return count;
}
int Company::AddNewCompany()
{
int count=0;
Company c;
clrscr();
count=CountinCompany();
c.c_ID=++count;
gotoxy(35,3);
for(int i=0;i<10;i++)
c.c_num[i]=0;
cout<<"Adding New Item To COMPANY";
gotoxy(5,5);
cout<<"Company ID:";
cout<<c.c_ID;
gotoxy(5,6);
cout<<"Company Name:";
cin>>c.c_name;
gotoxy(5,7);
cout<<"Company connected Person:";
cin>>c.c_person;
gotoxy(5,8);
cout<<"Address City:";
cin>>c.c_address;
gotoxy(5,9);
cout<<"Mobile Number:";
cin>>c.c_num;
gotoxy(5,10);
cout<<"Credit Amount:";
cin>>c.c_amt;
ofstream file;
file.open("cp.dat",ios::binary|ios::app);
file.write((char *)&c,sizeof(c));
file.close();
getch();
return 0;
}
int Company::ListCompany()
{
ifstream file;
Company c;
file.open("cp.dat",ios::binary);
int i=0,j=6;
clrscr();
gotoxy(35,3);
cout<<"All Available Company\n\n";
gotoxy(0,5);
cout<<"ID";
gotoxy(10,5);
cout<<"COMPANY";
gotoxy(30,5);
cout<<"ADDRESS";
gotoxy(45,5);
cout<<"PERSON";
gotoxy(60,5);
cout<<"CONTACT N0.";
gotoxy(74,5);
cout<<"CREDIT\n";
while(file.read((char *)&c,sizeof(c))!=NULL)
{
 gotoxy(i,j);
 cout<<c.c_ID;
 i=i+10;
 gotoxy(i,j);
 cout<<c.c_name;
 i=i+20;
 gotoxy(i,j);
 cout<<c.c_address;
 i=i+15;
 gotoxy(i,j);
 cout<<c.c_person;
 i=i+15;
 gotoxy(i,j);
 for(int a=0;a<10;a++)
 cout<<c.c_num[a];
 i=i+14;
 gotoxy(i,j);
 cout<<c.c_amt<<endl;
 i=0;
 j=j+1;
}
getch();
return 0;
}
int Company::UpdateCompany()
{
int id;
Company c;
clrscr();
fstream file1;
fstream file2;
file1.open("cp.dat",ios::in|ios::binary);
file2.open("stemp.dat",ios::out|ios::binary);
ifstream file;
file.open("cp.dat",ios::binary);
int i=0,j=6;
clrscr();
gotoxy(35,3);
cout<<"All Available Company\n\n";
gotoxy(0,5);
cout<<"ID";
gotoxy(10,5);
cout<<"COMPANY";
gotoxy(30,5);
cout<<"ADDRESS";
gotoxy(45,5);
cout<<"PERSON";
gotoxy(60,5);
cout<<"CONTACT N0.";
gotoxy(74,5);
cout<<"CREDIT\n";
while(file.read((char *)&c,sizeof(c))!=NULL)
{
 gotoxy(i,j);
 cout<<c.c_ID;
 i=i+10;
 gotoxy(i,j);
 cout<<c.c_name;
 i=i+20;
 gotoxy(i,j);
 cout<<c.c_address;
 i=i+15;
 gotoxy(i,j);
 cout<<c.c_person;
 i=i+15;
 gotoxy(i,j);
 for(int a=0;a<10;a++)
 cout<<c.c_num[a];
 i=i+14;
 gotoxy(i,j);
 cout<<c.c_amt<<endl;
 i=0;
 j=j+1;
}
cout<<"\nEnter ID of COMPANY to update its CREDIT:-->";
cin>>id;
while(file1.read((char *)&c,sizeof(c))!=NULL)
{
 if(c.c_ID!=id)
  {
   file2.write((char *)&c,sizeof(c));
  }
 else
  {
   if(id==c.c_ID)
  {
	clrscr();
	gotoxy(35,3);
	cout<<"Updating CREDIT AMOUNT of COMPANY";
	gotoxy(5,5);
	cout<<"Company ID:";
	cout<<c.c_ID;
	gotoxy(5,6);
	cout<<"Company Name:";
	cout<<c.c_name;
	gotoxy(5,7);
	cout<<"New Credit amount:";
	cin>>c.c_amt;
	file2.write((char *)&c,sizeof(c));
	cout<<"\n!!!!Updation Successfull!!!!";
      }
     }
   }
file1.close();
file2.close();
file1.open("cp.dat",ios::out|ios::binary);
file2.open("stemp.dat",ios::in|ios::binary);
while(file2.read((char *)&c,sizeof(c))!=NULL)
{
file1.write((char *)&c,sizeof(c));
}
file1.close();
file2.close();
getch();
return 0;
}
int Company::DeleteCompany()
{
int id,ID=0;
Company c;
clrscr();
fstream file1;
fstream file2;
file1.open("cp.dat",ios::in|ios::binary);
file2.open("stemp.dat",ios::out|ios::binary);
ifstream file;
file.open("cp.dat",ios::binary);
int i=0,j=6;
clrscr();
gotoxy(35,3);
cout<<"All Available Company\n\n";
gotoxy(0,5);
cout<<"ID";
gotoxy(10,5);
cout<<"COMPANY";
gotoxy(30,5);
cout<<"ADDRESS";
gotoxy(45,5);
cout<<"PERSON";
gotoxy(60,5);
cout<<"CONTACT N0.";
gotoxy(74,5);
cout<<"CREDIT\n";
while(file.read((char *)&c,sizeof(c))!=NULL)
{
 gotoxy(i,j);
 cout<<c.c_ID;
 i=i+10;
 gotoxy(i,j);
 cout<<c.c_name;
 i=i+20;
 gotoxy(i,j);
 cout<<c.c_address;
 i=i+15;
 gotoxy(i,j);
 cout<<c.c_person;
 i=i+15;
 gotoxy(i,j);
 for(int a=0;a<10;a++)
 cout<<c.c_num[a];
 i=i+14;
 gotoxy(i,j);
 cout<<c.c_amt<<endl;
 i=0;
 j=j+1;
}
cout<<"\nEnter ID of COMPANY to delete its details:-->";
cin>>id;
while(file1.read((char *)&c,sizeof(c))!=NULL)
{
 if(c.c_ID<id)
  {
   file2.write((char *)&c,sizeof(c));
  }
  if(id==c.c_ID)
  {
	ID=id;
	cout<<"\n!!!!Deletion Successfull!!!!";
      }
  if(c.c_ID>id)
  {
   c.c_ID=ID++;
   file2.write((char *)&c,sizeof(c));
  }
   }
file1.close();
file2.close();
file1.open("cp.dat",ios::out|ios::binary);
file2.open("stemp.dat",ios::in|ios::binary);
while(file2.read((char *)&c,sizeof(c))!=NULL)
{
file1.write((char *)&c,sizeof(c));
}
file1.close();
file2.close();
getch();
return 0;
}
int Company::CountinCompany()
{
 ifstream file;
 Company c;
 int count=0;
 file.open("cp.dat",ios::binary);
 if(file==NULL)
 count=0;
 while(file.read((char *)&c,sizeof(c)))
 {
  count++;
 }
 file.close();
 return count;
}
int Client::AddNewClient()
{
int count=0;
Client cl;
clrscr();
count=CountinClient();
cl.cl_ID=++count;
gotoxy(35,3);
cout<<"Adding New Item To CLIENT";
gotoxy(5,5);
cout<<"Client ID:";
cout<<cl.cl_ID;
gotoxy(5,6);
cout<<"Client Name:";
cin>>cl.cl_name;
gotoxy(5,7);
cout<<"Address City:";
cin>>cl.cl_address;
gotoxy(5,8);
cout<<"Mobile Number:";
cin>>cl.cl_num;
gotoxy(5,9);
cout<<"Credit Amount:";
cin>>cl.cl_amt;
ofstream file;
file.open("cl.dat",ios::binary|ios::app);
file.write((char *)&cl,sizeof(cl));
file.close();
getch();
return 0;
}
int Client::ListClient()
{
ifstream file;
Client cl;
file.open("cl.dat",ios::binary);
int i=0,j=6;
clrscr();
gotoxy(35,3);
cout<<"All Available Clients\n\n";
gotoxy(0,5);
cout<<"ID";
gotoxy(10,5);
cout<<"CLIENT NAME";
gotoxy(30,5);
cout<<"ADDRESS";
gotoxy(50,5);
cout<<"CONTACT N0.";
gotoxy(65,5);
cout<<"CREDIT\n";
while(file.read((char *)&cl,sizeof(cl))!=NULL)
{
 gotoxy(i,j);
 cout<<cl.cl_ID;
 i=i+10;
 gotoxy(i,j);
 cout<<cl.cl_name;
 i=i+20;
 gotoxy(i,j);
 cout<<cl.cl_address;
 i=i+20;
 gotoxy(i,j);
 for(int a=0;a<10;a++)
 cout<<cl.cl_num[a];
 i=i+15;
 gotoxy(i,j);
 cout<<cl.cl_amt<<endl;
 i=0;
 j=j+1;
}
getch();
return 0;
}
int Client::UpdateClient()
{
int id;
Client cl;
clrscr();
fstream file1;
fstream file2;
file1.open("cl.dat",ios::in|ios::binary);
file2.open("stemp.dat",ios::out|ios::binary);
ifstream file;
file.open("cl.dat",ios::binary);
int i=0,j=6;
clrscr();
gotoxy(35,3);
cout<<"All Available Clients\n\n";
gotoxy(0,5);
cout<<"ID";
gotoxy(10,5);
cout<<"CLIENT NAME";
gotoxy(30,5);
cout<<"ADDRESS";
gotoxy(50,5);
cout<<"CONTACT N0.";
gotoxy(65,5);
cout<<"CREDIT\n";
while(file.read((char *)&cl,sizeof(cl))!=NULL)
{
 gotoxy(i,j);
 cout<<cl.cl_ID;
 i=i+10;
 gotoxy(i,j);
 cout<<cl.cl_name;
 i=i+20;
 gotoxy(i,j);
 cout<<cl.cl_address;
 i=i+20;
 gotoxy(i,j);
 for(int a=0;a<10;a++)
 cout<<cl.cl_num[a];
 i=i+15;
 gotoxy(i,j);
 cout<<cl.cl_amt<<endl;
 i=0;
 j=j+1;
}
cout<<"\nEnter ID of CLIENT to update its CREDIT:-->";
cin>>id;
while(file1.read((char *)&cl,sizeof(cl))!=NULL)
{
 if(cl.cl_ID!=id)
  {
   file2.write((char *)&cl,sizeof(cl));
  }
 else
  {
   if(id==cl.cl_ID)
  {
	clrscr();
	gotoxy(35,3);
	cout<<"Updating CREDIT AMOUNT of CLIENT";
	gotoxy(5,5);
	cout<<"Client ID:";
	cout<<cl.cl_ID;
	gotoxy(5,6);
	cout<<"Client Name:";
	cout<<cl.cl_name;
	gotoxy(5,7);
	cout<<"New Credit amount:";
	cin>>cl.cl_amt;
	file2.write((char *)&cl,sizeof(cl));
	cout<<"\n!!!!Updation Successfull!!!!";
      }
     }
   }
file1.close();
file2.close();
file1.open("cl.dat",ios::out|ios::binary);
file2.open("stemp.dat",ios::in|ios::binary);
while(file2.read((char *)&cl,sizeof(cl))!=NULL)
{
file1.write((char *)&cl,sizeof(cl));
}
file1.close();
file2.close();
getch();
return 0;
}
int Client::DeleteClient()
{
int id,ID;
Client cl;
clrscr();
fstream file1;
fstream file2;
file1.open("cl.dat",ios::in|ios::binary);
file2.open("stemp.dat",ios::out|ios::binary);
ifstream file;
file.open("cl.dat",ios::binary);
int i=0,j=6;
clrscr();
gotoxy(35,3);
cout<<"All Available Clients\n\n";
gotoxy(0,5);
cout<<"ID";
gotoxy(10,5);
cout<<"CLIENT NAME";
gotoxy(30,5);
cout<<"ADDRESS";
gotoxy(50,5);
cout<<"CONTACT N0.";
gotoxy(65,5);
cout<<"CREDIT\n";
while(file.read((char *)&cl,sizeof(cl))!=NULL)
{
 gotoxy(i,j);
 cout<<cl.cl_ID;
 i=i+10;
 gotoxy(i,j);
 cout<<cl.cl_name;
 i=i+20;
 gotoxy(i,j);
 cout<<cl.cl_address;
 i=i+20;
 gotoxy(i,j);
 for(int a=0;a<10;a++)
 cout<<cl.cl_num[a];
 i=i+15;
 gotoxy(i,j);
 cout<<cl.cl_amt<<endl;
 i=0;
 j=j+1;
}
cout<<"\nEnter ID of CLIENT to delete its details:-->";
cin>>id;
while(file1.read((char *)&cl,sizeof(cl))!=NULL)
{
 if(cl.cl_ID<id)
  {
   file2.write((char *)&cl,sizeof(cl));
  }
   if(id==cl.cl_ID)
  {
	ID=id;
	cout<<"\n!!!!Deletion Successfull!!!!";
     }
   if(cl.cl_ID>id)
   {
    cl.cl_ID=ID++;
    file2.write((char *)&cl,sizeof(cl));
   }
   }
file1.close();
file2.close();
file1.open("cl.dat",ios::out|ios::binary);
file2.open("stemp.dat",ios::in|ios::binary);
while(file2.read((char *)&cl,sizeof(cl))!=NULL)
{
file1.write((char *)&cl,sizeof(cl));
}
file1.close();
file2.close();
getch();
return 0;
}
int Client::CountinClient()
{
 ifstream file;
 Client cl;
 int count=0;
 file.open("cl.dat",ios::binary);
 if(file==NULL)
 count=0;
 while(file.read((char *)&cl,sizeof(cl)))
 {
  count++;
 }
 file.close();
 return count;
}
int Sell::ItemSell()
{
clrscr();
int x,i,j;
Store s;
g:
  j=15,i=7;
   clrscr();
   gotoxy(5,1);
   cout<<"*********************************************************************";
   gotoxy(25,3);
   printf("Welcome to Sell Window");
   gotoxy(5,4);
   cout<<"*********************************************************************";
   printf("\n\nPlease choose option to perform operation:->");
   gotoxy(15,7);
   printf("New CLIENT");
   gotoxy(55,7);
   printf("REGISTERED CLIENT");
   gotoxy(35,9);
   printf("EXIT");
   gotoxy(j,i);

while((x=bioskey(0))!=75) // I took a value so that the loop continues.
{                         // no other reason for 75
 if(x==20480)//DownKey
  {
   if(i<=9)
   {
    j=35;
    i=9;
    gotoxy(j,i);
   }
  }
  else if(x==18432)//UpKey
  {
   if(i!=7)
   {
    j=15;
    i=7;
    gotoxy(j,i);
   }
  }
  else if(x==19712)//LeftKey
  {
    if(j<55&&i==7)
    {
     j=55;
     gotoxy(j,i);
    }
  }
  else if(x==19200)//RightKey
  {
   if(j!=15&&i==7)
   {
    j=15;
    gotoxy(j,i);
   }
  }
  else if(x==7181)
  {
    clrscr();
    if(j==15&&i==7)
    {
     AddNewClient();
     cout<<"\nNew Client added successfully";
     getch();
     BillGenerate();
     getch();
     return 0;
    }
    else if(j==55&&i==7)
    {
     BillGenerate();
     getch();
     return 0;
    }
    else if(j==35&&i==9)
    {
     cout<<"SEll Window Closing...";
     getch();
     return 0;
	 }
}
}
 return 0;
}
void Sell::CalcProfit()
{
time_t tt;
tm *ti;
fstream file;
char ch[20];
float i=6,j=9,x=1,totalrate=0,totalprice=0,qty=0,rate=0,profit;
file.open("Bill.txt",ios::in);
clrscr();
int gd=DETECT,gm;
initgraph(&gd,&gm,"c://turboc3//bgi");
rectangle(10,20,610,450);
time(&tt);
ti=localtime(&tt);
gotoxy(5,3);
cout<<"*********************************************************************";
gotoxy(6,4);
cout<<"\tMedical Store\t\t    DATE:";
gotoxy(5,5);
cout<<"*********************************************************************";
gotoxy(45,4);
cout<<asctime(ti);
gotoxy(26,6);
cout<<"--->Total Sell Details<---";
gotoxy(5,7);
cout<<"---------------------------------------------------------------------";
gotoxy(6,8);
cout<<"S.No.";
gotoxy(14,8);
cout<<"Item Name";
gotoxy(31,8);
cout<<"Rate";
gotoxy(38,8);
cout<<"Price";
gotoxy(45,8);
cout<<"Quantity";
gotoxy(62,8);
cout<<"Total Price";
gotoxy(5,24);
cout<<"Cost:";
gotoxy(28,24);
cout<<"Total Sell:";
gotoxy(5,25);
cout<<"---------------------------------------------------------------------";
while(!file.eof())
{
i=6;
gotoxy(i,j);
if(ch!=NULL);
cout<<x++;
file>>ch;
file>>ch;
i=i+8;
gotoxy(i,j);
cout<<ch;
file>>ch;
rate=atoi(&ch[0]);
i=i+17;
gotoxy(i,j);
cout<<ch;
file>>ch;
i=i+7;
gotoxy(i,j);
cout<<ch;
file>>ch;
qty=atoi(&ch[0]);
totalrate+=rate*qty;
i=i+7;
gotoxy(i,j);
cout<<ch;
file>>ch;
totalprice+=atoi(&ch[0]);
i=i+17;
gotoxy(i,j);
cout<<ch;
j=j+1;
}
gotoxy(10,24);
cout<<totalrate;
gotoxy(39,24);
cout<<totalprice;
profit=((totalprice/totalrate)*100)-100;
gotoxy(50,24);
cout<<"PROFIT: "<<profit<<" %";
getch();
closegraph();
supermain();

}
void Sell::BillGenerate()
{
int qty,id,price,clid;
char ch;
Store s;
Client cl;
fstream billfile;
billfile.open("BillTemp.txt",ios::out);
cl.ListClient();
cout<<"\nSelect Client by ID:";
cin>>clid;
h:
s.ListStock();
cout<<"\nEnter ID to Sell ITEM:";
cin>>id;
g:
cout<<"\nEnter Quantity to SELL:";
cin>>qty;
clrscr();
fstream file1;
fstream file2;
fstream file3,file4;
fstream file;
file1.open("st.dat",ios::in|ios::binary);
file2.open("stemp.dat",ios::out|ios::binary);
file3.open("cl.dat",ios::in|ios::binary);
file4.open("cltemp.dat",ios::out|ios::binary);
file.open("Bill.txt",ios::app);
while(file1.read((char *)&s,sizeof(s))!=NULL)
{
 if(id!=s.item_ID)
 {
  file2.write((char *)&s,sizeof(s));
 }
 else
 {
  if(qty<=s.item_qty)
  {
  s.item_qty-=qty;
  price=qty*s.item_price;
  while(file3.read((char *)&cl,sizeof(cl))!=NULL)
  {
   if(clid==cl.cl_ID)
  {
   cl.cl_amt+=price;
   file<<cl.cl_name<<" ";
   billfile<<cl.cl_name<<" ";
   file4.write((char *)&cl,sizeof(cl));
  }
  else
  file4.write((char *)&cl,sizeof(cl));
  }
  file<<s.item_name<<" "<<s.item_rate<<" "<<s.item_price<<" "<<qty<<" "<<price<<endl;
  billfile<<s.item_name<<" "<<s.item_price<<" "<<qty<<" "<<price<<endl;
  file2.write((char *)&s,sizeof(s));
  }
  else
  {
  clrscr();
  cout<<"\n!!!!!!!!!!!!Insufficient Quantity!!!!!!!!!!!!!!";
  cout<<"\nAvailable Quantity of "<<s.item_name<<":"<<s.item_qty;
  goto g;
  }
 }
 }
file1.close();
file2.close();
file1.open("st.dat",ios::out|ios::binary);
file2.open("stemp.dat",ios::in|ios::binary);
while(file2.read((char *)&s,sizeof(s))!=NULL)
{
file1.write((char *)&s,sizeof(s));
}
file3.close();
file4.close();
file3.open("cl.dat",ios::out|ios::binary);
file4.open("cltemp.dat",ios::in|ios::binary);

while(file4.read((char *)&cl,sizeof(cl))!=NULL)
{
file3.write((char *)&cl,sizeof(cl));
}
file3.close();
file4.close();
file1.close();
file2.close();
gotoxy(20,30);
cout<<"Sell More Item(y/n):";
cin>>ch;
if(ch=='y'||ch=='y')
goto h;
else
gotoxy(20,31);
billfile.close();
file.close();
ShowBill();
}

int StoreFunction()
{
clrscr();
int x,i,j;
Store s;
g:
  j=5,i=7;
   clrscr();
   gotoxy(5,2);
   cout<<"*********************************************************************";
   gotoxy(25,3);
   printf("Welcome to Stock Window");
   gotoxy(5,4);
   cout<<"---------------------------------------------------------------------";
   gotoxy(5,7);
   printf("ADD NEW STOCK");
   gotoxy(25,7);
   printf("UPDATE STOCK");
   gotoxy(45,7);
   printf("DELETE STOCK");
   gotoxy(65,7);
   printf("LIST STOCK");
   gotoxy(45,9);
   printf("EXIT");
   gotoxy(j,i);

while((x=bioskey(0))!=75) // I took a value so that the loop continues.
{                         // no other reason for 75
 if(x==20480)//DownKey
  {
   if(i<=9)
   {
    j=45;
    i=9;
    gotoxy(j,i);
   }
  }
  else if(x==18432)//UpKey
  {
   if(i!=7)
   {
    j=5;
    i=7;
    gotoxy(j,i);
   }
  }
  else if(x==19712)//LeftKey
  {
    if(j<65&&i==7)
    {
     j=j+20;
     gotoxy(j,i);
    }
  }
  else if(x==19200)//RightKey
  {
   if(j!=5&&i==7)
   {
    j=j-20;
    gotoxy(j,i);
   }
  }
  else if(x==7181)
  {
    clrscr();
    if(j==5&&i==7)
    {
     s.AddNewStock();
     cout<<"\nNew Stock Added Successfully";
     cout<<"\n\t\tPress any Key To Close This Window";
    }
    else if(j==25&&i==7)
    {
     s.UpdateStock();
     cout<<"\n\t\tPress any Key To Close This Window";
    }
    else if(j==45&&i==7)
    {
     s.DeleteStock();
     cout<<"\n\t\tPress any Key To Close This Window";
    }
    else if(j==65&&i==7)
    {
     s.ListStock();
     cout<<"\n\t\tPress any Key To Close This Window";
    }
    else if(j==45&&i==9)
    {
     cout<<"Stock Window Closing...";
     getch();
     supermain();
     return 0;
    }
  getch();
  goto g;
}
}
return 0;
}
int CompanyFunction()
{
clrscr();
int x,i,j;
Company c;
  j=5,i=7;
  g:
   clrscr();
   gotoxy(5,2);
   cout<<"*********************************************************************";
   gotoxy(25,3);
   printf("Welcome to Company Window");
   gotoxy(5,4);
   cout<<"---------------------------------------------------------------------";
   gotoxy(5,7);
   printf("ADD NEW COMPANY");
   gotoxy(25,7);
   printf("UPDATE COMPANY");
   gotoxy(45,7);
   printf("DELETE COMPANY");
   gotoxy(65,7);
   printf("LIST COMPANY");
   gotoxy(45,9);
   printf("EXIT");
   gotoxy(j,i);

while((x=bioskey(0))!=75) // I took a value so that the loop continues.
{                         // no other reason for 75
 if(x==20480)//DownKey
  {
   if(i<=9)
   {
    j=45;
    i=9;
    gotoxy(j,i);
   }
  }
  else if(x==18432)//UpKey
  {
   if(i!=7)
   {
    j=5;
    i=7;
    gotoxy(j,i);
   }
  }
  else if(x==19712)//LeftKey
  {
    if(j<65&&i==7)
    {
     j=j+20;
     gotoxy(j,i);
    }
  }
  else if(x==19200)//RightKey
  {
   if(j!=5&&i==7)
   {
    j=j-20;
    gotoxy(j,i);
   }
  }
  else if(x==7181)
  {
    clrscr();
    if(j==5&&i==7)
    {
     c.AddNewCompany();
     cout<<"\nNew Company Added Successfully";
     cout<<"\n\t\tPress any Key To Close This Window";
    }
    else if(j==25&&i==7)
    {
     c.UpdateCompany();
     cout<<"\n\t\tPress any Key To Close This Window";
    }
    else if(j==45&&i==7)
    {
     c.DeleteCompany();
     cout<<"\n\t\tPress any Key To Close This Window";
    }
    else if(j==65&&i==7)
    {
     c.ListCompany();
     cout<<"\n\t\tPress any Key To Close This Window";
    }
    else if(j==45&&i==9)
    {
     cout<<"Company Window Closing...";
     getch();
     supermain();
     return 0;
    }
  getch();
  goto g;
}
}
return 0;
}
int ClientFunction()
{
clrscr();
int x,i,j;
Client cl;
  j=5,i=7;
 g:
   clrscr();
   gotoxy(5,2);
   cout<<"*********************************************************************";
   gotoxy(25,3);
   printf("Welcome to Client Window");
   gotoxy(5,4);
   cout<<"---------------------------------------------------------------------";
   gotoxy(5,7);
   printf("ADD NEW CLIENT");
   gotoxy(25,7);
   printf("UPDATE CLIENT");
   gotoxy(45,7);
   printf("DELETE CLIENT");
   gotoxy(65,7);
   printf("LIST CLIENT");
   gotoxy(45,9);
   printf("EXIT");
   gotoxy(j,i);

while((x=bioskey(0))!=75) // I took a value so that the loop continues.
{                         // no other reason for 75
 if(x==20480)//DownKey
  {
   if(i<=9)
   {
    j=45;
    i=9;
    gotoxy(j,i);
   }
  }
  else if(x==18432)//UpKey
  {
   if(i!=7)
   {
    j=5;
    i=7;
    gotoxy(j,i);
   }
  }
  else if(x==19712)//LeftKey
  {
    if(j<65&&i==7)
    {
     j=j+20;
     gotoxy(j,i);
    }
  }
  else if(x==19200)//RightKey
  {
   if(j!=5&&i==7)
   {
    j=j-20;
    gotoxy(j,i);
   }
  }
  else if(x==7181)
  {
    clrscr();
    if(j==5&&i==7)
    {
     cl.AddNewClient();
     cout<<"\nNew Client Added Successfully";
     cout<<"\n\t\tPress any Key To Close This Window";
    }
    else if(j==25&&i==7)
    {
     cl.UpdateClient();
     cout<<"\n\t\tPress any Key To Close This Window";
    }
    else if(j==45&&i==7)
    {
     cl.DeleteClient();
     cout<<"\n\t\tPress any Key To Close This Window";
    }
    else if(j==65&&i==7)
    {
     cl.ListClient();
     cout<<"\n\t\tPress any Key To Close This Window";
    }
    else if(j==45&&i==9)
    {
     cout<<"Client Window Closing...";
     getch();
     supermain();
     return 0;
    }
   getch();
   goto g;
}
}
return 0;
}
int SellFunction()
{
clrscr();
int x,i,j;
Sell sl;
   j=15,i=7;
 g:
   clrscr();
   gotoxy(5,2);
   cout<<"*********************************************************************";
   gotoxy(25,3);
   printf("Welcome to Sell Window");
   gotoxy(5,4);
   cout<<"---------------------------------------------------------------------";
   gotoxy(15,7);
   printf("SELL ITEM");
   gotoxy(35,7);
   printf("SHOW ALL SELLs");
   gotoxy(25,9);
   printf("EXIT");
   gotoxy(j,i);

while((x=bioskey(0))!=75) // I took a value so that the loop continues.
{                         // no other reason for 75
 if(x==20480)//DownKey
  {
   if(i<=9)
   {
    j=25;
    i=9;
    gotoxy(j,i);
   }
  }
  else if(x==18432)//UpKey
  {
   if(i!=7)
   {
    j=15;
    i=7;
    gotoxy(j,i);
   }
  }
  else if(x==19712)//LeftKey
  {
    if(j<35&&i==7)
    {
     j=j+20;
     gotoxy(j,i);
    }
  }
  else if(x==19200)//RightKey
  {
   if(j!=15&&i==7)
   {
    j=j-20;
    gotoxy(j,i);
   }
  }
  else if(x==7181)
  {
    clrscr();
    if(j==15&&i==7)
    {
     sl.ItemSell();
    }
    else if(j==35&&i==7)
    {
     sl.CalcProfit();
    }
    else if(j==25&&i==9)
    {
     cout<<"Sell Window Closing...";
     getch();
     supermain();
     return 0;
    }
    return 0;
}
}
getch();
goto g;
}
int supermain()
{
clrscr();
int x;
  int j=10;
  int i=7;
 g:
   clrscr();
   gotoxy(5,2);
   cout<<"*********************************************************************";
   gotoxy(25,3);
   printf("SRM MEDICAL STORE MANAGEMENT SYSTEM");
   gotoxy(5,4);
   cout<<"---------------------------------------------------------------------";
   gotoxy(10,7);
   printf("STOCK");
   gotoxy(30,7);
   printf("COMPANY");
   gotoxy(50,7);
   printf("CLIENT");
   gotoxy(70,7);
   printf("SELL");
   gotoxy(40,9);
   printf("EXIT");
   gotoxy(j,i);

while((x=bioskey(0))!=75) // I took a value so that the loop continues.
{                         // no other reason for 75
 if(x==20480)//DownKey
  {
   if(i<=9)
   {
    j=40;
    i=9;
    gotoxy(j,i);
   }
  }
  else if(x==18432)//UpKey
  {
   if(i!=7)
   {
    j=10;
    i=7;
    gotoxy(j,i);
   }
  }
  else if(x==19712)//LeftKey
  {
    if(j<70&&i==7)
    {
     j=j+20;
     gotoxy(j,i);
    }
  }
  else if(x==19200)//RightKey
  {
   if(j!=10&&i==7)
   {
    j=j-20;
    gotoxy(j,i);
   }
  }
  else if(x==7181)//EnterKey
  {
    clrscr();
    if(j==10&&i==7)
    {
     StoreFunction();
    }
    else if(j==30&&i==7)
    {
     CompanyFunction();
    }
    else if(j==50&&i==7)
    {
     ClientFunction();
    }
    else if(j==70&&i==7)
    {
     SellFunction();
    }
    else if(j==40&&i==9)
    {
     cout<<"Thankyou for visit...";
     getch();
     exit(1);
     return 0;
    }
    return 0;
  }
}
return 0;
}
void ShowBill()
{
time_t tt;
tm *ti;
fstream file,tfile;
char ch[20],name[20];
int i=6,j=11,x=1,total=0;
tfile.open("Billtemp.txt",ios::in);
tfile>>name;
tfile.close();
file.open("Billtemp.txt",ios::in);
clrscr();
int gd=DETECT,gm;
initgraph(&gd,&gm,"c://turboc3//bgi");
setbkcolor(RED);
rectangle(10,20,610,450);
time(&tt);
ti=localtime(&tt);
gotoxy(5,3);
cout<<"*********************************************************************";
gotoxy(6,4);
cout<<"\t\t\t\tSRM Medical Store";
gotoxy(5,5);
cout<<"*********************************************************************";
gotoxy(5,7);
cout<<"NAME: ";
cout<<name;
gotoxy(45,7);
cout<<asctime(ti);
gotoxy(5,9);
cout<<"---------------------------------------------------------------------";
gotoxy(6,10);
cout<<"S.No.";
gotoxy(14,10);
cout<<"Item Name";
gotoxy(31,10);
cout<<"Item Price";
gotoxy(45,10);
cout<<"Item Quantity";
gotoxy(62,10);
cout<<"Total Price";
gotoxy(50,24);
cout<<"Grand Total:";
gotoxy(5,25);
cout<<"---------------------------------------------------------------------";
while(!file.eof())
{
i=6;
file>>ch;
gotoxy(i,j);
if(ch!=NULL);
cout<<x++;
file>>ch;
i=i+8;
gotoxy(i,j);
cout<<ch;
file>>ch;
i=i+17;
gotoxy(i,j);
cout<<ch;
file>>ch;
i=i+14;
gotoxy(i,j);
cout<<ch;
file>>ch;
total+=atoi(&ch[0]);
i=i+17;
gotoxy(i,j);
cout<<ch;
j=j+1;
}
gotoxy(64,24);
cout<<total;
getch();
closegraph();
supermain();
}

