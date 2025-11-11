#include <iostream>
#include <cstring>
#include <cmath>
using namespace std;

/* ============================================================
1. Function to find Prime Number
============================================================ */
bool isPrime(int n){
    if(n<=1) return false;
    for(int i=2;i<=n/2;i++)
        if(n%i==0) return false;
    return true;
}
/* Output:
Enter number: 7
Prime
*/

/* ============================================================
2. Function to print Fibonacci Series
============================================================ */
void fibonacci(int n){
    int a=0,b=1,c;
    cout<<a<<" "<<b<<" ";
    for(int i=3;i<=n;i++){
        c=a+b; cout<<c<<" ";
        a=b; b=c;
    }
}
/* Output:
Fibonacci: 0 1 1 2 3 5 8
*/

/* ============================================================
3. Bubble Sort Function
============================================================ */
void bubbleSort(int a[], int n){
    for(int i=0;i<n-1;i++)
        for(int j=0;j<n-i-1;j++)
            if(a[j]>a[j+1]) swap(a[j], a[j+1]);
}
/* Output:
Sorted: 1 2 3 4 5
*/

/* ============================================================
4. Copy String Function
============================================================ */
void copyString(char t[], char s[]){
    int i=0;
    while(s[i]!='\0'){
        t[i]=s[i];
        i++;
    }
    t[i]='\0';
}
/* Output:
Copied string: Hello
*/

/* ============================================================
5. Count Words in String
============================================================ */
int countWords(char s[]){
    int c=0;
    for(int i=0;s[i]!='\0';i++)
        if(s[i]==' ') c++;
    return c+1;
}
/* Output:
Words: 4
*/

/* ============================================================
6. Binary Search Function
============================================================ */
int binarySearch(int a[], int n, int x){
    int l=0, r=n-1;
    while(l<=r){
        int m=(l+r)/2;
        if(a[m]==x) return m;
        else if(a[m]<x) l=m+1;
        else r=m-1;
    }
    return -1;
}
/* Output:
Found at index 2
*/

/* ============================================================
7. Sum of Two Matrices
============================================================ */
void sumMatrix(int a[3][3], int b[3][3]){
    int c[3][3];
    for(int i=0;i<3;i++){
        for(int j=0;j<3;j++){
            c[i][j]=a[i][j]+b[i][j];
            cout<<c[i][j]<<" ";
        }
        cout<<endl;
    }
}
/* Output:
Matrix Sum:
4 6 8
5 7 9
3 5 7
*/

/* ============================================================
8. Sum of Diagonal Elements
============================================================ */
int sumDiagonal(int a[3][3]){
    int s=0;
    for(int i=0;i<3;i++) s+=a[i][i];
    return s;
}
/* Output:
Diagonal sum = 15
*/

/* ============================================================
9. Swap Using Call-by-Reference
============================================================ */
void swapRef(int &x, int &y){
    int t=x; x=y; y=t;
}
/* Output:
Before: 3 5
After: 5 3
*/

/* ============================================================
10. Class Student
============================================================ */
class Student{
public:
    string name;
    int roll;
    float marks;
    void input(){
        name="Rahul"; roll=1; marks=85.5;
    }
    void show(){
        cout<<name<<" "<<roll<<" "<<marks;
    }
};
/* Output:
Rahul 1 85.5
*/

/* ============================================================
11. Class Car (Multiple Objects)
============================================================ */
class Car{
public:
    string brand;
    int price;
    void set(string b,int p){ brand=b; price=p; }
    void show(){ cout<<brand<<" "<<price<<endl; }
};
/* Output:
BMW 5000000
Audi 4500000
*/

/* ============================================================
12. Encapsulation: Bank Account
============================================================ */
class Bank{
private:
    int balance;
public:
    Bank(){ balance=0; }
    void deposit(int a){ balance+=a; }
    void withdraw(int a){ balance-=a; }
    void show(){ cout<<"Balance: "<<balance; }
};
/* Output:
Balance: 300
*/

/* ============================================================
13. Single Inheritance
============================================================ */
class Person{
public:
    string name;
    int age;
};
class Student2: public Person{
public:
    int marks;
    void show(){
        cout<<name<<" "<<age<<" "<<marks;
    }
};
/* Output:
Ravi 20 90
*/

/* ============================================================
14. Function Overloading
============================================================ */
class Calculator{
public:
    int add(int a,int b){ return a+b; }
    double add(double a,double b){ return a+b; }
};
/* Output:
5
7.5
*/

/* ============================================================
15. Abstraction: Abstract Shape Class
============================================================ */
class Shape{
public:
    virtual float area()=0;
};

class Circle : public Shape{
public:
    float r;
    Circle(float x){ r=x; }
    float area(){ return 3.14*r*r; }
};

class Rectangle : public Shape{
public:
    float l,b;
    Rectangle(float x,float y){ l=x; b=y; }
    float area(){ return l*b; }
};
/* Output:
Circle Area: 78.5
Rectangle Area: 20
*/

/* ===========================================================
