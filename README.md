#include <iostream>
#include <iomanip>

using namespace std;

int pizza_size();
int toppings();
void total(double size, double top);
void cart();

int main() {

    cout<< "Welcome to Ole Fashioned Pizzas!" << endl << endl;

    double size_total;
    size_total = pizza_size();
    cout<<endl;


    double topping_total;
    topping_total = toppings();
    cout<<endl;


    total(size_total, topping_total);

    cout<< endl << endl;

    cart();

    return 0;
}

int pizza_size(){

    int size;
    double size_total;
    double price = 0;

    cout<< "What size pizza would you like?" << endl;
    cout<< "#1. Small - $8" << endl;
    cout<< "#2. Medium - $11" << endl;
    cout<< "#3. Large - $14" << endl;
    cout<< "#4. Mitchell - $16" << endl;
    cin>> size;

    if(size){

        if(size == 1){
            cout<< "You chose a small pizza." << endl;
            size_total = price + 8;
        }
        if(size == 2){
            cout<< "You chose a medium pizza." << endl;
            size_total = price + 11;
        }
        if(size == 3){
            cout<< "You chose a large pizza." << endl;
            size_total = price + 14;
        }
        if(size == 4){
            cout<< "You chose a Mitchell pizza." << endl;
            size_total = price + 16;
        }
        if(size < 1) {
            cout << "You chose a Large pizza." << endl;
            size_total = price + 14;
        }
        if(size > 4) {
            cout << "You chose a Large pizza." << endl;
            size_total = price + 14;
        }
    }
    return size_total;
}

int toppings(){

    int toppings;
    double topping_total;

    cout<< "Toppings are $2.00 each." << endl;
    cout<< "How many toppings would you like on your pizza?" << endl;
    cin>> toppings;

    if(toppings >= 0) {
        cout << "You chose " << toppings << " toppings." << endl;
        topping_total = toppings * 2;
    }
    else
        cout<< "That is not a correct number." << endl;


    return topping_total;
}

void total(double size, double top) {


    double total;
    double tax;
    double grand_total;
    total = size + top;

    cout << fixed << showpoint << setprecision(2);
    tax = total * 0.08;
    grand_total = total + tax;

    cout << "Subtotal    $" << total << endl;
    cout << "Tax         $" << tax << endl;
    cout << "Grand Total $" << grand_total << endl << endl;
}

void cart(){

    const int ITEMS = 6;
    double price[ITEMS];
    int count;
    double total = 0;
    int position;
    double price_change;
    double total2 = 0;

    for(count = 0; count < ITEMS; count++)
    {
        cout<< "Enter the price of item " << (count + 1) << ": "<< endl;
        cin>> price[count];
    }

    cout<< endl;
    cout<< "The price of each item is: " << endl;

    for(count = 0; count < ITEMS; count++)
    {
        cout<< "$" << price[count] << endl;
    }

    cout << fixed << showpoint << setprecision(2);

    for(count = 0; count < ITEMS; count++) {
        total += price[count];
    }
    cout<< "The total is $" << total << endl << endl;

    cout<< "Pick an item you would like to change the price of. Item #" << endl;
    cin>> position;


        if(position == 1){
            cout<< "What price would you like to change this item to?" << endl;
            cin>> price_change;
            price[0] = price_change;
        }
        if(position == 2){
            cout<< "What price would you like to change this item to?" << endl;
            cin>> price_change;
            price[1] = price_change;
        }
        if(position == 3){
            cout<< "What price would you like to change this item to?" << endl;
            cin>> price_change;
            price[2] = price_change;
        }
        if(position == 4){
            cout<< "What price would you like to change this item to?" << endl;
            cin>> price_change;
            price[3] = price_change;
        }
        if(position == 5){
            cout<< "What price would you like to change this item to?" << endl;
            cin>> price_change;
            price[4] = price_change;
        }
        if(position == 6){
            cout<< "What price would you like to change this item to?" << endl;
            cin>> price_change;
            price[5] = price_change;
        }
        if(position >= 7){
            cout<< "You did not pick a valid item number." << endl;
        }
        if( position <= 0){
            cout<< "You did not pick a valid item number." << endl;
        }

    cout<< endl;
    cout<< "The price of each item is now: " << endl;

    for(count = 0; count < ITEMS; count++)
    {
        cout<< "$" << price[count] << endl;
    }

    for(count = 0; count < ITEMS; count++) {
        total2 += price[count];
    }
    cout<< "The total is $" << total2 << endl << endl;

}
