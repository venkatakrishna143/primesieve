# primesieve

#include <bits/stdc++.h>
using namespace std;

void primesieve(int n)
{
    bool prime[n + 1];
    memset(prime, 1, sizeof(prime));

    for (int p = 2; p * p <= n; p++)
    {

        if (prime[p] == 1)
        {

            for (int i = p * p; i <= n; i += p)
                prime[i] = 0;
        }
    }

    for (int p = 2; p <= n; p++)
        if (prime[p])

            cout << p << " ";

}

int main()
{
    int n;
    cin>>n;
    primesieve(n);
    return 0;
}
