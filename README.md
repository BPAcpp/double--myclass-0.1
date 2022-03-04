/*The idea was to solve the problem of adding 10 fractional numbers 0.1 and when comparing with an integer variable 1, the result was true
*/


/*The problem occurred when assigning the sum of three or more objects due to an error in writing the overload of the + operator (dabla & operator + (...))
after he removed the icon "link" everything worked, as I conceived*/


/*There is also one limitation. You can only work with "one number after a comma"
For example:
1.5 But not 1.56*/



#include<iostream>
#include<string>


using namespace std;
class dabla
{
public:




    dabla() {
        this->a = 0;
        this->b = 0;

    }


    dabla(int ap, int bp) {

        if (bp >= 10) {

            cout << "Error b>=10\n";

        }
        else {
            this->a = ap;
            this->b = bp;
        }
    }





    /////////////////
    int getA() {
        return this->a;

    }




    int getB() {
        return this->b;

    }



    dabla& operator+(dabla& b)
    {
        dabla temp;

        if (this->b + b.b >= 10) {
            temp.b = this->b + b.b - 10;
            temp.a = this->a + b.a;
            temp.a = temp.a + 1;
        }
        else {
            temp.a = this->a + b.a;
            temp.b = this->b + b.b;
        }


        return temp;
    }





    double transformate(dabla a) {
        double temp;

        temp = (double)a.getA() + ((double)a.getB() / 10);
        this->c = temp;
        return temp;
    }

    double getC() {
        return (double)c;
    }


    dabla& operator=(dabla b) {
        this->a = b.a;
        this->b = b.b;
        return *this;
    }


    string for_cout_s(dabla a) {
        this->transformate(a);
        return to_string(this->a) + "." + to_string(this->b);
    }

    bool operator==(double b) {

        return c == b;

    }
protected:
    int a = 0;
    int b = 0;
    double c = 0;
};

int main() {
    setlocale(LC_ALL, "ru");


    dabla a(0, 1);

    dabla b(0, 1);

    dabla c(0, 0);

    c = b + a + a;
    cout << c.for_cout_s(c);




    double qwerty = 1;

    if (qwerty == c.transformate(c)) {
        cout << "qwerty = 1";
    }

    return 0;
}





