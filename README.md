Source   : https://www.geeksforgeeks.org/implementation-diffie-hellman-algorithm/

Theme    : Cyrptography

Tittle   : Implementation-Of-Diffie Hellman-Cyrptograph-Key-Exchanger

Kelompok 15 

Member:

Nur Hikmatul Maulida       17.83.0070

Dia Putera Idiana Kusuma   17.83.0083

===============================================================================

                                    Implementation-Of-Diffie Hellman-Cyrptograph-Key-Exchanger

===============================================================================

Introduction Aplication :

Diffie- Hellman key exchange adalah metode pertukaran kunci kriptografi yang bersifat rahasia secara bersamaan antara dua pihak yang dapat digunakan untuk komunikasi rahasia untuk bertukar data melalui jaringan publik.Pada project kali ini menggunakan bahasa pemrograman C++ yang didukung oleh 2 fungsi sederhana berpokok pada pembuatan kunci utama dalam kriptografi ini.

Diffie-Hellman Algoritm :

X1 = (G^A) mod P >> (X2^B) mod P = Ka

X2 = (G^B) mod P >> (X1^A) mod P = Kb

P = Bilangan Prima
G = Kunci Publik 1
X = Kunci Publik 2
A = Kunci Private 1
B = Kunci Private 2
Ka = Kunci yang dibagikan A
Kb = Kunci yang dibagikan B

===================================================================================
algorithm difielman
long long int power(long long int a, long long int b,  long long int N) 
{  
    if (b == 1) 
        return a; 
  
    else
        return (((long long int)pow(a, b)) % N); 
} 
==================================================================================
main code
int main(){
	int P, N, G, a, x, b, y, ka, kb;
Failed:
    cout<<"Input Prime Key [P]: "; cin>>N;

          P = KeyPrima(N);

              if(P==0)
              {
             		cout<<"Key Succesfull"<<endl;
            	}

             else 
              {
              	cout<<"Key Failed"<<endl;

                goto Failed;
              }


    cout<<"Input Public Key [G]: "; cin>>G; 

    cout<<"Input Private Key a: "; cin>>a; 
    x = power(G, a, N);

    cout << "Value Private Key a is : "<< x << endl;

    cout<<"Input Private Key b: "; cin>>b;

    y= power(G, b, N);

   cout << "Value Private Key b is : "<< y << endl;
  
  ka = power(y, a, N); // Secret key for Alice 
cout << "Secret Key a is : "<< ka << endl;
  kb = power(x, b, N); // Secret key for Bob  
cout << "Secret Key b is : "<< kb << endl;

  return 0;  
}


Fungction Explained :
Fungction disini merupakan fungsi dengan nilai balik yang dimana Fungsi dengan nilai balik dapat mengembalikan suatu nilai ke dalam fungsi utama.


int Key_P;                        //mendeklarasikan dan menginisalisasikan bahwa Key_P adalah objek dengan input data integer.
  
      int KeyPrima(int n)         //menempatkan nilai n pada objek KeyPrima yang dimana n akan mendapatkan input dari fungsi main.
        {
            int i;

            for(i=2; i<=n/2; i++) //perulangan dalam menentukan bilangan prima atau tidaknya nilai yang diinputkan dari fungsi main.
           
            {
                if(n%i==0)        //percabangan apa bila nilai n mod i adalah 0 maka hasilnya adalah bukan bilangan prima

                {Key_P++;}        // mengulangi variable Key_P ditambah 1 untuk.

            } 

              return Key_P;
        }   

            
