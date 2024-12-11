//complex-number

#include<iostream>
using namespace std;

class Complex{
public:
	float real;
	float img;

	Complex(){
		real = 0;
		img = 0;
	}

	Complex(float a, float b){
		real = a;
		img = b;
	}

	void print(){
		cout << real << " + " << img << "i" << endl;
	}

	Complex operator+(Complex c2){
		Complex temp;
		temp.real = real + c2.real;
		temp.img = img + c2.img;
		return temp;
	}	
};

Complex operator*(Complex c1, Complex c2){
	Complex temp;
	temp.real = (c1.real * c2.real) - (c1.img * c2.img);
	temp.img = (c1.real * c2.img) + (c1.img * c2.real);

	return temp;
}

ostream& operator<<(ostream& COUT, Complex c1){
	COUT << c1.real << " + " << c1.img << "i" << endl;
}

istream& operator>>(istream& CIN, Complex& c){
	CIN >> c.real >> c.img;
}

int main()
{
	Complex z1; // default constructor
	Complex z2(2,6); // parameterised constructor

	Complex z3 = z1 + z2; // operator+

	cout << z3 << z2; // operator<<

	Complex z4;
	cout << "Enter real and img part for a complex number: ";
	cin >> z4; // operator>>

	cout << z4; // operator<<
  cout << z3*z4; // operator*

}
