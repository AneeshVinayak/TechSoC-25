#include <iostream>
using namespace std;

int main()
{
    string s;
    cout << "Enter shift value: ";
    int shift;
    cin >> shift;

    cin.ignore(); // <-- important, clear newline from buffer

    cout << "Enter message to be encoded: ";
    getline(cin, s);

    int i;
    char ch;
    int n = s.length();
    string enc = "";
    shift = shift % 26;

   
    for(i=0;i<n;i++)
    {
        ch=s[i];
