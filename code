#include <iostream>
#include <list>
#include <memory> // Для использования std::unique_ptr

// Базовый класс Building
class Building {
protected:
    std::string name; // Название здания
    int floors;       // Количество этажей

public:
    // Конструктор
    Building(const std::string& name, int floors)
        : name(name), floors(floors) {}

    // Виртуальный деструктор
    virtual ~Building() {}

    // Виртуальная функция для вывода информации о здании
    virtual void display() const {
        std::cout << "Building Name: " << name << ", Floors: " << floors << std::endl;
    }

    // Методы для изменения имени и количества этажей
    void setName(const std::string& newName) { name = newName; }
    void setFloors(int newFloors) { floors = newFloors; }
};

// Класс ResidentialBuilding, наследующий от Building
class ResidentialBuilding : public Building {
private:
    int apartments; // Количество квартир

public:
    // Конструктор
    ResidentialBuilding(const std::string& name, int floors, int apartments)
        : Building(name, floors), apartments(apartments) {}

    // Переопределение функции display()
    void display() const override {
        std::cout << "Residential Building Name: " << name
            << ", Floors: " << floors
            << ", Apartments: " << apartments << std::endl;
    }

    // Методы для получения и изменения количества квартир
    int getApartments() const { return apartments; }
    void setApartments(int newApartments) { apartments = newApartments; }
};

// Класс OfficeBuilding, наследующий от Building
class OfficeBuilding : public Building {
private:
    int offices; // Количество офисов

public:
    // Конструктор
    OfficeBuilding(const std::string& name, int floors, int offices)
        : Building(name, floors), offices(offices) {}

    // Переопределение функции display()
    void display() const override {
        std::cout << "Office Building Name: " << name
            << ", Floors: " << floors
            << ", Offices: " << offices << std::endl;
    }

    // Методы для получения и изменения количества офисов
    int getOffices() const { return offices; }
    void setOffices(int newOffices) { offices = newOffices; }
};

// Функция для изменения характеристик здания
void modifyBuilding(Building* building, const std::string& newName, int newFloors) {
    building->setName(newName);
    building->setFloors(newFloors);
}

int main() {
    // Создаем контейнер для хранения указателей на объекты Building
    std::list<std::unique_ptr<Building>> buildings;

    // Заполняем контейнер объектами ResidentialBuilding и OfficeBuilding
    buildings.emplace_back(std::make_unique<ResidentialBuilding>("Residential A", 10, 50));
    buildings.emplace_back(std::make_unique<OfficeBuilding>("Office B", 15, 30));
    buildings.emplace_back(std::make_unique<ResidentialBuilding>("Residential C", 5, 20));
    buildings.emplace_back(std::make_unique<OfficeBuilding>("Office D", 20, 40));

    // Используем итераторы STL для вывода информации о каждом здании в контейнере
    for (const auto& building : buildings) {
        building->display();
    }

    // Изменяем характеристики одного из зданий
    modifyBuilding(buildings.front().get(), "Modified Residential A", 12);

    // Выводим информацию о зданиях после изменения
    std::cout << "\nAfter modification:\n";
    for (const auto& building : buildings) {
        building->display();
    }

    return 0;
}
