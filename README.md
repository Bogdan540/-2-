#include <iostream>
#include <vector>
#include <numeric> // Для std::gcd

// Функція для обчислення НСК двох чисел
long long lcm(long long a, long long b) {
    return (a / std::gcd(a, b)) * b;
}

// Функція для обчислення НСК множини чисел
long long find_lcm(const std::vector<long long>& numbers) {
    long long result = numbers[0];
    for (size_t i = 1; i < numbers.size(); ++i) {
        result = lcm(result, numbers[i]);
    }
    return result;
}

int main() {
    int r;
    std::cin >> r;
    std::vector<long long> numbers(r);
    
    for (int i = 0; i < r; ++i) {
        std::cin >> numbers[i];
    }
    
    long long result = find_lcm(numbers);
    std::cout << result << std::endl;
    
    return 0;
}
