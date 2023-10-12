#include <iostream>
#include <cstdlib>
#include <ctime>
#include <cmath>

int main()
{
    std::srand(static_cast<unsigned int>(std::time(nullptr)));

    int totalPoints = 0;

    for (int i = 0; i < 5; ++i)
    {
        int xi, yi;
        std::cout << "Введите координаты выстрела " << (i + 1) << " (xi yi): ";
        std::cin >> xi >> yi;

        int random_xi = std::rand() % 11 - 5;
        int random_yi = std::rand() % 11 - 5;

        int radius = std::sqrt((xi + random_xi) * (xi + random_xi) + (yi + random_yi) * (yi + random_yi));

        int points = 5 - radius;

        if ((points & (1 << 31)))
        {
            points = 0;
        }

        totalPoints += points;
    }

    std::cout << "Сумма баллов: " << totalPoints << std::endl;

    if (totalPoints < 10)
    {

        std::cout << "Лузер" << std::endl;
    }

    return 0;
}
