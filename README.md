# matrix-multiplication
#include<iostream>
    using namespace std;

    int main() {
        int m, n, p, q;

        // Input the dimensions of the matrices
        cout << "Enter row of first matrix: ";
        cin >> m;
        cout << "Enter column of first matrix: ";
        cin >> n;

        cout << "Enter row of 2nd matrix: ";
        cin >> p;
        cout << "Enter column of 2nd matrix: ";
        cin >> q;

        // Matrix multiplication is possible if n == p
        if (n == p) {
            int a[m][n], b[p][q], re[m][q];

            // Input first matrix
            cout << "Enter elements of first matrix: \n";
            for (int i = 0; i < m; i++) {
                for (int j = 0; j < n; j++) {
                    cin >> a[i][j];
                }
            }

            // Input second matrix
            cout << "Enter elements of second matrix: \n";
            for (int i = 0; i < p; i++) {
                for (int j = 0; j < q; j++) {
                    cin >> b[i][j];
                }
            }

            // Initialize the result matrix with zeros
            for (int i = 0; i < m; i++) {
                for (int j = 0; j < q; j++) {
                    re[i][j] = 0;
                }
            }

            // Perform matrix multiplication
            for (int i = 0; i < m; i++) {
                for (int j = 0; j < q; j++) {
                    for (int k = 0; k < n; k++) {
                        re[i][j] += a[i][k] * b[k][j];
                    }
                }
            }

            // Output the result matrix
            cout << "Resultant matrix is: \n";
            for (int i = 0; i < m; i++) {
                for (int j = 0; j < q; j++) {
                    cout << re[i][j] << " ";
                }
                cout << endl;
            }
        } else {
            cout << "Matrix multiplication not possible. Columns of first matrix must be equal to rows of second matrix.\n";
        }

        return 0;
    }
