//faily
#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main()
{
int temp, i;
cout « "A:" « endl;
ofstream fileA("A.txt");
for ( i = 0; i < 3; i++)
{
cin » temp;
fileA « temp;
fileA « endl;
}
fileA.close();
cout « endl « "B:" « endl;
ofstream fileB("B.txt");
for ( i = 0; i < 3; i++)
{
cin » temp;
fileB « temp;
fileB « endl;
}
fileB.close();
int A[3] = {};
int B[3] = {};
i = 0;
string path = "A.txt";
ifstream fin;
fin.open(path);
for (int i = 0; i < 3; ++i)
{
fin » A[i];
}
fin.close();
i = 0;
string path2 = "B.txt";
ifstream fin2;
fin2.open(path2);
for (int i = 0; i < 3; ++i)
{
fin2 » B[i];
}
fin2.close();
for (int j = 0; j < 2; j++) {
for (int i = 0; i < 2; i++) {
if (A[i] > A[i + 1]) {
temp = A[i];
A[i] = A[i + 1];
A[i + 1] = temp;
}
}
}
for (int j = 0; j < 2; j++) {
for (int i = 0; i < 2; i++) {
if (B[i] > B[i + 1]) {
temp = B[i];
B[i] = B[i + 1];
B[i + 1] = temp;
}
}
}
ofstream fileC("C.txt");
int C[6] = {};
for (i = 0; i < 3; i++)
{
C[i] = A[i];
C[3 + i] = B[i];
}
for (int j = 0; j < 5; j++) {
for (int i = 0; i < 5; i++) {
if (C[i] > C[i + 1]) {
temp = C[i];
C[i] = C[i + 1];
C[i + 1] = temp;
}
}
}
for (i = 0; i < 6; i++)
{
fileC « C[i];
fileC « endl;
}
fileC.close();
return 0;
}
