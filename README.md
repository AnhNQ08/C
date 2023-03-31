#include <stdio.h>

int main () {
	int m, n, p, q, i, j;
	scanf("%d%d%d%d", &m, &n, &p, &q);
	long long a[m][n], b[n][p], c[p][q], t[m][p], z[m][q];
	for(i = 0; i < m; i++) {
		for(j = 0; j < n; j++) {
			scanf("%lld", &a[i][j]);
		}
	}
	for(i = 0; i < n; i++) {
		for(j = 0; j < p; j++) {
			scanf("%lld", &b[i][j]);	
		}
	}
	for(i = 0; i < p; i++) {
		for(j = 0; j < q; j++) {
			scanf("%lld", &c[i][j]);
		}
	}
	for(i = 0; i < m; i++) {
		for(j = 0; j < p; j++) {
			t[i][j] = 0;
			for(int k = 0; k < n; k++) {
				t[i][j] += a[i][k] * b[k][j];
			}
		}
	}
	for(i = 0; i < m; i++) {
		int tong = 0;
		for(j = 0; j < q; j++) {
			z[i][j] = 0;
			for(int k = 0; k < p; k++) {
				z[i][j] += t[i][k] * c[k][j];
			}
		}
	}
	for(i = 0; i < m; i++) {
		for(j = 0; j < p; j++) {
			printf("%lld ", z[i][j]);
		}
		printf("\n");
	}
}
