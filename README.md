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
#include <stdio.h> 
#include <math.h>
#include <locale.h>
int main() {
setlocale(LC_ALL, "Russian");
int nachal;
unsigned short hod = 0, 
max = 0,
optimal_hod = 0,
summa;
do {
    printf("Введите начальную сумму в копейках: ");
	scanf_s("%d", &nachal); 
} while (nachal < 0 || nachal >= 10000);
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
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

int main() {
    setlocale(LC_ALL, "Russian");

    const int size = 10000;

    int n;
    double a, b;
    bool valid = false;

    while (!valid) {
        printf("Введите количество элементов массива N (от 1 до %d): ", size);
        if (scanf("%d", &n) == 1 && n > 0 && n <= size) {
            valid = true;
        }
        else {
            printf("Некорректный ввод. Попробуйте еще раз.\n");
        }
    }

    valid = false;
    while (!valid) {
        printf("Введите границы диапазона A и B через пробел: ");
        if (scanf("%lf %lf", &a, &b) == 2) {
            valid = true;
        }
        else {
            scanf("%*s");
            printf("Некорректный ввод. Попробуйте еще раз.\n");
        }
    }

    if (a > b) {
        double temp = a;
        a = b;
        b = temp;
    }

    
    double arr[size];
    double filtered[size];

    printf("\nИсходный массив:\n");
    int count = 0;
    for (int i = 0; i < n; i++) {
        if (n > 1) {
            arr[i] = 11.0 + ((double)i / (n - 1)) * (22.0 - 11.0);
        }
        else {
            arr[i] = 11.0;
        }

        printf("%.2f ", arr[i]);
        if (arr[i] >= a && arr[i] <= b) {
            filtered[count] = arr[i];
            count++;
        }
    }
    printf("\n");

    if (count == 0) {
        printf("\nЭлементов в диапазоне [%.2f, %.2f] не найдено.\n", a, b);
    }
    else {
        for (int i = 1; i < count; i++) {
            double key = filtered[i];
            int j = i - 1;
            while (j >= 0 && filtered[j] < key) {
                filtered[j + 1] = filtered[j];
                j--;
            }
            filtered[j + 1] = key;
        }

        printf("\nЭлементы в диапазоне [%.2f, %.2f] по невозрастанию:\n", a, b);
        for (int i = 0; i < count; i++) {
            printf("%.2f ", filtered[i]);
        }
        printf("\n");
    }
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <locale.h>
#include <stdlib.h>
#include <time.h>
double calculate_final_score(const double* scores, int m) {
    double sum = 0;
    double max_score = scores[0];
    double min_score = scores[0];

    for (int i = 0; i < m; i++) {
        sum += scores[i];
        if (scores[i] > max_score) max_score = scores[i];
        if (scores[i] < min_score) min_score = scores[i];
    }
    return (sum - max_score - min_score) / (m - 2);
}

int main() {
    setlocale(LC_ALL, "Russian");
    srand((unsigned int)time(NULL));

    int n = 2 + rand() % (10 - 2 + 1); 
    int m = 3 + rand() % (10 - 3 + 1); 

    printf("Сгенерировано: Спортсменов = %d, Судей = %d\n\n", n, m);

    const int size = 10;
    double all_scores[size][size]; 

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < m; j++) {
            all_scores[i][j] = (rand() % 101) / 10.0;
        }
    }

    
    printf("Результаты судейства:\n");
    for (int i = 0; i < n; i++) {
        printf("Спортсмен %2d: ", i + 1);
        for (int j = 0; j < m; j++) {
            printf("%4.1f ", all_scores[i][j]);
        }
        printf("\n");
    }
    printf("\n");

    
    printf("Итоговые результаты спортсменов:\n");
    for (int i = 0; i < n; i++) {
        double result = calculate_final_score(all_scores[i], m);
        printf("Спортсмен %d: %.2f\n", i + 1, result);
    }

    return 0;
}
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <locale.h>
#include <stdlib.h> 
#include <time.h>
#define MAX_PLACE 50 
int main() {
    setlocale(LC_ALL, "Russian");
    int n, m;
    srand(time(NULL));
    do {
        printf("Введите количество лыжников (N) и количество стартов (M): ");
        scanf("%d %d", &n, &m);

        if (n <= 0 || m <= 0) {
            printf("Ошибка! Числа должны быть строго больше нуля. Повторите ввод.\n\n");
        }
    } while (n <= 0 || m <= 0);

    int sums[1000];
    int last_stages[1000];  

    printf("\n--- Сгенерированные результаты соревнований ---\n");
    for (int i = 0; i < n; i++) {
        sums[i] = 0;
        printf("Лыжник №%d занял места: ", i + 1);

        for (int j = 0; j < m; j++) {
            int place = rand() % MAX_PLACE + 1;
            printf("%d ", place);

            sums[i] += place;
            if (j == m - 1) {
                last_stages[i] = place;
            }
        }
        printf("| Сумма: %d\n", sums[i]);
    }

    int winner_index = 0;

    for (int i = 1; i < n; i++) {
        if (sums[i] < sums[winner_index]) {
            winner_index = i;
        }
        else if (sums[i] == sums[winner_index]) {
            if (last_stages[i] < last_stages[winner_index]) {
                winner_index = i;
            }
        }
    }

    printf("\n=== ИТОГИ ===\n");
    printf("Победитель в общем зачете: Лыжник №%d\n", winner_index + 1);
    printf("Сумма мест: %d, Место на последнем этапе: %d\n", sums[winner_index], last_stages[winner_index]);

    return 0;
}
    return 0;
}
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>
int main() {
    setlocale(LC_ALL, "Russian");
    const int MAX_SIZE = 100;

    int n, m;
    bool valid = false;

    double a[MAX_SIZE];
    double b[MAX_SIZE];
    double c[MAX_SIZE * 2];

    
    while (!valid) {
        printf("Введите размер первого массива N (0 < N <= %d): ", MAX_SIZE);
        if (scanf("%d", &n) == 1) {
            if (n <= 0) {
                printf("Ошибка: размер должен быть больше 0.\n");
            }
            else if (n > MAX_SIZE) {
                printf("Ошибка: размер не должен превышать %d.\n", MAX_SIZE);
            }
            else {
                valid = true;
            }
        }
        else {
            printf("Ошибка: нужно ввести целое число!\n");
            scanf("%*s");
        }
    }

    valid = false;

    
    while (!valid) {
        printf("Введите размер второго массива M (0 < M <= %d): ", MAX_SIZE);
        if (scanf("%d", &m) == 1) {
            if (m <= 0) {
                printf("Ошибка: размер должен быть больше 0.\n");
            }
            else if (m > MAX_SIZE) {
                printf("Ошибка: размер не должен превышать %d.\n", MAX_SIZE);
            }
            else {
                valid = true;
            }
        }
        else {
            printf("Ошибка: нужно ввести целое число!\n");
            scanf("%*s");
        }
    }

    
    for (int i = 0; i < n; i++) {
        a[i] = ((double)rand() / RAND_MAX) * 99.0 + 1.0;
    }

    
    for (int i = 0; i < m; i++) {
        b[i] = ((double)rand() / RAND_MAX) * 99.0 + 1.0;
    }

    
    printf("\nСгенерированный первый массив A:\n");
    for (int i = 0; i < n; i++) {
        printf("a[%d] = %.2f\n", i, a[i]);
    }

    printf("\nСгенерированный второй массив B:\n");
    for (int i = 0; i < m; i++) {
        printf("b[%d] = %.2f\n", i, b[i]);
    }

    int idx = 0;

    for (int i = 0; i < n; i += 2) {
        c[idx++] = a[i];
    }

    for (int i = 1; i < m; i += 2) {
        c[idx++] = b[i];
    }

    int k = idx;
    printf("\nРезультирующий массив (размер %d):\n", k);
    if (k == 0) {
        printf("Массив оказался пустым.\n");
    }
    else {
        for (int i = 0; i < k; i++) {
            printf("%.2f ", c[i]);
        }
        printf("\n");
    }

    return 0;
}
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <locale.h>
#include <stdlib.h>
#include <time.h>

int main() {
    setlocale(LC_ALL, "Russian");

    const int MAX_SKIERS = 1000;
    const int MAX_STAGES = 50;
    const int MAX_PLACE = 50;

    int n_input, m_input;
    srand((unsigned int)time(NULL));

    int res;

    do {
        printf("Введите количество лыжников (N) и количество стартов (M): ");
        res = scanf("%d %d", &n_input, &m_input);

        if (res != 2 || n_input <= 0 || n_input > MAX_SKIERS ||
            m_input <= 0 || m_input > MAX_STAGES) {
            scanf("%*[^\n]%*c");

            printf("Ошибка! Введите два целых числа в допустимых пределах.\n");
            printf("N: от 1 до %d, M: от 1 до %d\n\n", MAX_SKIERS, MAX_STAGES);
        }
    } while (res != 2 || n_input <= 0 || n_input > MAX_SKIERS ||
        m_input <= 0 || m_input > MAX_STAGES);

    const int n = n_input;
    const int m = m_input;

    int results[MAX_SKIERS][MAX_STAGES];

    printf("\n--- Сгенерированные результаты соревнований ---\n");

    for (int i = 0; i < n; ++i) {
        int sum = 0;
        printf("Лыжник №%d занял места: ", i + 1);

        for (int j = 0; j < m; ++j) {
            const int place = rand() % MAX_PLACE + 1;
            results[i][j] = place;
            sum += place;
            printf("%d ", place);
        }

        const int last_place = results[i][m - 1];
        printf("| Сумма: %d\n", sum);
    }

    int winner_index = 0;
    int best_sum = 0;

    for (int j = 0; j < m; ++j) {
        best_sum += results[0][j];
    }
    const int best_last = results[0][m - 1];

    for (int i = 1; i < n; ++i) {
        int current_sum = 0;
        for (int j = 0; j < m; ++j) {
            current_sum += results[i][j];
        }
        const int current_last = results[i][m - 1];

        if (current_sum < best_sum) {
            best_sum = current_sum;
            winner_index = i;
        }
        else if (current_sum == best_sum) {
            if (current_last < best_last) {
                best_sum = current_sum;
                winner_index = i;
            }
        }
    }

    int final_sum = 0;
    for (int j = 0; j < m; ++j) {
        final_sum += results[winner_index][j];
    }
    const int final_last = results[winner_index][m - 1];

    printf("\n=== ИТОГИ ===\n");
    printf("Победитель в общем зачёте: Лыжник №%d\n", winner_index + 1);
    printf("Сумма мест: %d, Место на последнем этапе: %d\n", final_sum, final_last);

    return 0;
}


