#Задачи с лабораторной
2 лаба
#include <iostream>
#import <cmath>
#//int main()
#//{
    #//float a = 0.5;
    #//float b = 0.5;
    #//double y = sqrt((pow(a, pow(sin(b), 2) + cos(pow(b, 3))) + cbrt(pow(b, 2))) / pow(fabs((a * tan(b)) / (1 - exp(sqrt(a)))), 1.0 / 4.0));
    #//std::cout << y << std::endl;
    #//return 0;
#}

Задача с 3 лабы (18)
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <math.h>
#include <locale.h>
int main() {
    int N;
    setlocale(LC_ALL, "Rus");
    do {
        printf("Введите число N (от 1 до 1000000): ");
        scanf("%d", &N) != 1;
    } while (N < 1);
        

        int bestP = 1;
        int bestQ = 1;
        int minDiff = N;

        for (int Q = 1; Q * Q <= N; Q++) {

            for (int P = 1; P <= Q; P++) {
                int sum = P * P + Q * Q;
                int diff = abs(N - sum);


                if (diff < minDiff) {
                    minDiff = diff;
                    bestP = P;
                    bestQ = Q;
                }
            }
        }
    }
        printf("P = %d, Q = %d\n", bestP, bestQ);

        return 0;
    }
}



#include <iostream>
#include <cmath>
int main()
{
	unsigned char  hours = 2;
	unsigned char minutes = 43;
	hours = hours % 12;
	float min_grrrr = minutes * 6;
	float housr_grrr = (hours * 30) + (minutes * 0.5);
	float diff = abs(housr_grrr - min_grrrr);
	float d = (diff > 180) ? 360.0 - diff : diff;
	printf("diff = %.1f\n", diff);
	return 0;
}


#include <iostream>
#include <stdio.h>

int main()

{
	int r, k;
	setlocale(LC_ALL, "RUS");
	printf(" рубли копейки: ");
	scanf_s("%d %d",&r, &k);
	unsigned long long money = r * 100 + k;
	unsigned long long mgr_money = money;
	int bstep = 0;
	int s = 0;
	do {
		money = money - 29;
		money = (money % 100) * 100 + (money / 100);
		money > mgr_money ? (mgr_money = money, bstep = s) : 0;
		s++;
	} while (s <= 100);
	printf("%d\n", bstep);
	return 0;
}
#include <stdio.h> #include <math.h> #include <locale.h>
int main() { setlocale(LC_ALL, "Russian"); int nachal; unsigned short hod = 0, max = 0, optimal_hod = 0, summa; do { printf("Введите начальную сумму в копейках: "); scanf_s("%d", &nachal); } while (nachal < 0 || nachal >= 10000);
summa = nachal;
max = summa;
if (summa >= 29)
    do {
        hod++;
        summa -= 29;
        summa = summa % 100 * 100 + summa / 100;
        if (summa > max) {
            max = summa;
            optimal_hod = hod;
        }
    } while (summa >= 29 && summa != nachal);
printf("%d-%d-%d", nachal, max, optimal_hod);
}
#include <stdio.h>
#include <math.h> 
#include <locale.h>
int main() {
    setlocale(LC_ALL, "Russian"); 
    int nachal;
    unsigned short hod = 0, max = 0, optimal_hod = 0, summa; 
    do 
    {
        printf("Введите начальную сумму в копейках  (сумма > 0) : ");
        scanf_s("%d", &nachal); 
    } 
    while (nachal < 0 || nachal >= 10000);
    summa = nachal;
    max = summa;
    if (summa >= 29)
        do {
            hod++;
            summa -= 29;
            summa = summa % 100 * 100 + summa / 100;
            if (summa > max) {
                max = summa;
                optimal_hod = hod;
            }
        } while (summa >= 29 && summa != nachal);
        printf("%d-%d-%d", nachal, max, optimal_hod);
}
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

int main() {
    setlocale(LC_ALL, "Russian");

    int N;
    do {
        printf("Введите число N (от 1 до 1000000): ");
    } while (scanf("%d", &N) != 1 || N < 1 || N > 1000000);

    int bestP = 1;
    int bestQ = 1;
    int minDiff = N;

    for (int Q = 1; Q * Q <= N; Q++) {
        for (int P = 1; P <= Q; P++) {
            int sum = P * P + Q * Q;
            int diff = abs(N - sum);
            if (diff < minDiff) {
                minDiff = diff;
                bestP = P;
                bestQ = Q;
            }
        }
    }

    printf("P = %d, Q = %d\n", bestP, bestQ);

    return 0;
}



#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
int main() {
    setlocale(LC_ALL, "Russian");
    int n;
    printf("Введите количество четырехугольников: ");
    if (scanf("%d", &n) != 1) return 1; 
    int k1 = 0;
    int k2 = 0; 
    for (int i = 1; i <= n; ++i) {
        double a, b, c, d;
        printf("Введите стороны %d-го четырехугольника: ", i);

        
        if (scanf("%lf %lf %lf %lf", &a, &b, &c, &d) != 4) {
            printf("Ошибка ввода!\n");
            return 1;
        }
        if (a == b && b == c && c == d) {
            k1 = k1 + 1;
        }
        else if (a == c && b == d) {
            k2 = k2 + 1;
        }
    }
    printf("РОМБОВ - %d, ПАРАЛЛЕЛОГРАММОВ - %d\n", k1, k2);
    return 0;
}
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <math.h>
#include <locale.h>

int main() {
    setlocale(LC_ALL, "Russian");
    int n;
    double p;
    int K = 0;

    do {
        printf("Введите число треугольников n (больше 0): ");
        scanf("%d", &n);
        
        if (n <= 0) {
            printf("Ошибка! Число треугольников не может быть 0 или меньше. Введите заново.\n\n");
        }
    } while (n <= 0);

    do {
        printf("Ввести периметр P (больше 0): ");
        scanf("%lf", &p);
        
        if (p <= 0) {
            printf("Ошибка! Периметр должен быть положительным числом. Введите заново.\n\n");
        }
    } while (p <= 0);

    double x1, y1, x2, y2, x3, y3;
    for (int i = 0; i < n; i++) {
        printf("\nТреугольник %d:\n", i + 1);
        printf("Координаты первой вершины (x y): ");
        scanf("%lf %lf", &x1, &y1);

        printf("Координаты второй вершины (x y): ");
        scanf("%lf %lf", &x2, &y2);

        printf("Координаты третьей вершины (x y): ");
        scanf("%lf %lf", &x3, &y3);
        
        
        double a = sqrt((x2 - x1) * (x2 - x1) + (y2 - y1) * (y2 - y1));
        double b = sqrt((x3 - x1) * (x3 - x1) + (y3 - y1) * (y3 - y1));
        double c = sqrt((x3 - x2) * (x3 - x2) + (y3 - y2) * (y3 - y2));
        
        if ((a + b + c > p) &&
            ((a * a + b * b < c * c) || (b * b + c * c < a * a) || (a * a + c * c < b * b))) {
            K++;
        }
    }
    
    printf("\nЧисло треугольников, удовлетворяющих условию: %d\n", K);

    return 0;
}
#define _CRT_SECURE_NO_WARNINGS
#include <locale.h>
#include <stdio.h>

int main() {
    setlocale(LC_ALL, "Russian");
    double S;
    int valid = 0;

    // Цикл ввода без break, continue и getchar
    while (valid == 0) {
        printf("Введите значение S (S > 1): ");
        
        if (scanf("%lf", &S) != 1) {
            printf("Ошибка ввода. Пожалуйста, введите число.\n");
            scanf("%*s"); // Очищаем неверный ввод (заменяет getchar)
        } 
        else {
            if (S <= 1.0) {
                printf("Ошибка ввода: значение S должно быть больше 1 (вы ввели %.2lf).\n", S);
            } else {
                valid = 1; // Устанавливаем флаг, чтобы выйти из цикла ввода
            }
        }
    }

    if (S >= 12.0) {
        printf("Сумма этой последовательности никогда не превысит 12.\n");
        printf("Для заданного S = %.2lf решения не существует.\n", S);
        return 0;
    }

    double sum = 0.0;
    int n = 1;
    double power_of_two = 1.0;
    while (sum <= S) {
        double term = (n * n) / power_of_two;
        sum += term;
        if (sum <= S) {
            n++;
            power_of_two *= 2.0;
        }
    }
    printf("\n--- Цикл while ---\n");
    printf("Минимальное количество элементов: %d\n", n);
    printf("Достигнутая сумма: %lf\n", sum);

    sum = 0.0;
    n = 1;
    power_of_two = 1.0;
    do {
        double term = (n * n) / power_of_two;
        sum += term;
        if (sum <= S) {
            n++;
            power_of_two *= 2.0;
        }
    } while (sum <= S);
    printf("\n--- Цикл do-while ---\n");
    printf("Минимальное количество элементов: %d\n", n);
    printf("Достигнутая сумма: %lf\n", sum);

    sum = 0.0;
    n = 1;
    power_of_two = 1.0;
    for (; sum <= S; ) {
        double term = (n * n) / power_of_two;
        sum += term;
        if (sum <= S) {
            n++;
            power_of_two *= 2.0;
        }
    }
    printf("\n--- Цикл for ---\n");
    printf("Минимальное количество элементов: %d\n", n);
    printf("Достигнутая сумма: %lf\n", sum);

    return 0;
}
#define _CRT_SECURE_NO_WARNINGS
#include <locale.h>
#include <stdio.h>

int main() {
    setlocale(LC_ALL, "Russian");

    long long k = 0;
    int Valid = 0;

    while (Valid == 0) {
        printf("Введите число K (K <= 1e9): ");
        if (scanf("%lld", &k) != 1) {
            printf("Ошибка: введено не число! Попробуйте снова.\n");
            scanf("%*s");
        }
        else {
            if (k < 0 || k > 1000000000LL) {
                printf("Ошибка! Попробуйте снова.\n");
            }
            else {
                Valid = 1; 
            }
        }
    }

    if (k == 0) {
        printf("\nРезультат (любым способом): 0\n");
        return 0;
    }

    printf("\n");

    printf("Результат через while:   ");
    for (int i = 0; i <= 9; i++) {
        long long temp = k;
        while (temp > 0) {
            int digit = temp % 10;
            if (digit == i) {
                printf("%d", i);
            }
            temp /= 10;
        }
    }
    printf("\n");

    printf("Результат через for:     ");
    for (int i = 0; i <= 9; i++) {
        for (long long temp = k; temp > 0; temp /= 10) {
            int digit = temp % 10;
            if (digit == i) {
                printf("%d", i);
            }
        }
    }
    printf("\n");
    printf("Результат через do-while: ");
    for (int i = 0; i <= 9; i++) {
        long long temp = k;
        do {
            int digit = temp % 10;
            if (digit == i) {
                printf("%d", i);
            }
            temp /= 10;
        } while (temp > 0);
    }
    printf("\n");

    return 0;
}
