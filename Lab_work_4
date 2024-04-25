#include <iostream>
#include <cmath>

double calculate_series_sum(double x, double e) {
    if (e > 1.0) {
        return 0.0; // Если e больше 1, сумма ряда равна 0
    }

    double term = 1.0; // Первый член ряда
    double total_sum = term; // Сумма ряда
    int k = 0; // Счетчик для степени и факториала

    // Вычисляем члены ряда до тех пор, пока очередной член больше e
    while (std::abs(term) >= e) {
        k++;
        // Вычисляем следующий член ряда
        term = std::pow(-1, k) / (tgamma(k + 1) * tgamma(k + 3)) * std::pow(x / 2, 2 * k);
        total_sum += term;
    }

    return total_sum;
}

int main() {
    double x, e;

    setlocale(LC_ALL,"RUS");

    // Запрос у пользователя значения x
    std::cout << "Введите значение x: ";
    std::cin >> x;
    if (std::cin.fail()) {
        std::cout << "Некорректный ввод для x. Пожалуйста, введите число." << std::endl;
        return 1;
    }

    // Запрос у пользователя значения e
    std::cout << "Введите значение e (точность): ";
    std::cin >> e;
    if (std::cin.fail()) {
        std::cout << "Некорректный ввод для e. Пожалуйста, введите число." << std::endl;
        return 1;
    }

    // Проверка на допустимость значения e
    if (e > 1.0) {
        std::cout << "Значение e должно быть меньше или равно 1. Вычисление невозможно." << std::endl;
        return 1;
    }

    // Вычисление суммы ряда
    double result = calculate_series_sum(x, e);
    std::cout << "Сумма ряда с точностью e = " << e << " при x = " << x << " равна " << result << std::endl;

    return 0;
}
