#include <iostream>
#include <string>
using namespace std;

struct Account {
    string username;
    string password;
};

const int N = 5;
Account as[N] = {
    { "clarabella", "muuuu" },
    { "micky", "minnie" },
    { "minnie", "topolino"},
    { "paperino", "quack" },
    { "pluto", "bau"}
};
Account a { "micky", "minnie" };

string login_seq_r(Account &a, Account as[], int n) {
    if (n < 1)
        return "Impossibile eseguire l'accesso";
    if (a.username == as[0].username)
        if(a.password == as[0].password)
            return "Login!";
        else
            return "Password errata!";
    return login_seq_r(a, as + 1, n - 1);
}

string login_seq_i(Account &a, Account as[], int n) {
    for (int i = 0; i < n; ++i) {
        if (a.username == as[i].username)
            if (a.password == as[i].password)
                return "Login!";
            else
                return "Password errata!";
    }
    return "Impossibile eseguire l'accesso";
}

string login_bin_r(Account &a, Account as[], int begin, int end) {
    if (begin >= end)
        return "Impossibile eseguire l'accesso";
    int center = (begin + end) / 2;
    if (a.username == as[center].username)
            if (a.password == as[center].password)
                return "Login!";
            else
                return "Password errata!";
    if (a.username < as[center].username)
        return login_bin_r(a, as, begin, center);
    else
        return login_bin_r(a, as, center + 1, end);
        
}

string login_bin_i(Account &a, Account as[], int end) {
    int begin = 0;
    
    while (begin < end) {
        int center = (begin + end) / 2;
        if (a.username == as[center].username)
                if (a.password == as[center].password)
                    return "Login!";
                else
                    return "Password errata!";
        if (a.username < as[center].username)
            end = center;
        else
            begin = center + 1;
    }
    return "Impossibile eseguire l'accesso";
}


int main() {
    cout << "username: ";
    cin >> a.username;
    cout << "password: ";
    cin >> a.password;

    cout << login_seq_r(a, as, N) << "\n";
    cout << login_seq_i(a, as, N) << "\n";
    cout << login_bin_r(a, as, 0, N) << "\n";
    cout << login_bin_i(a, as, N) << "\n";
    
    return 0;
}
