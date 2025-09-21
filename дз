#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
    
    Node(int value) : data(value), next(nullptr) {}
};

// Перша функція: створення списку з даних, введених з клавіатури
Node* createList() {
    Node* head = nullptr;
    Node* tail = nullptr;
    
    cout << "Введіть числа для створення списку (введіть -1 для завершення):" << endl;
    
    while (true) {
        int value;
        cout << "Введіть число: ";
        cin >> value;
        
        if (value == -1) {
            break;
        }
        
        Node* newNode = new Node(value);
        
        if (head == nullptr) {
            head = newNode;
            tail = newNode;
        } else {
            tail->next = newNode;
            tail = newNode;
        }
    }
    
    return head;
}

// Друга функція: вставка елемента після заданого
void insertAfter(Node* &head, int targetValue, int newValue) {
    Node* current = head;
    
    while (current != nullptr) {
        if (current->data == targetValue) {
            Node* newNode = new Node(newValue);
            newNode->next = current->next;
            current->next = newNode;
            return;
        }
        current = current->next;
    }
    
    cout << "Елемент " << targetValue << " не знайдено у списку." << endl;
}

// Третя функція: вставка елемента перед заданим
void insertBefore(Node* &head, int targetValue, int newValue) {
    // Якщо список порожній
    if (head == nullptr) {
        cout << "Список порожній." << endl;
        return;
    }
    
    // Якщо елемент знаходиться на початку списку
    if (head->data == targetValue) {
        Node* newNode = new Node(newValue);
        newNode->next = head;
        head = newNode;
        return;
    }
    
    Node* current = head;
    
    // Шукаємо елемент, що передує цільовому
    while (current->next != nullptr) {
        if (current->next->data == targetValue) {
            Node* newNode = new Node(newValue);
            newNode->next = current->next;
            current->next = newNode;
            return;
        }
        current = current->next;
    }
    
    cout << "Елемент " << targetValue << " не знайдено у списку." << endl;
}

// Допоміжна функція для виведення списку
void printList(Node* head) {
    Node* current = head;
    cout << "Список: ";
    while (current != nullptr) {
        cout << current->data << " ";
        current = current->next;
    }
    cout << endl;
}

// Допоміжна функція для видалення списку (щоб уникнути витоку пам'яті)
void deleteList(Node* &head) {
    while (head != nullptr) {
        Node* temp = head;
        head = head->next;
        delete temp;
    }
}

int main() {
    // Створення списку
    Node* head = createList();
    printList(head);
    
    // Демонстрація вставки після заданого елемента
    int target, value;
    cout << "\nВставка ПІСЛЯ заданого елемента:" << endl;
    cout << "Введіть елемент, після якого вставити: ";
    cin >> target;
    cout << "Введіть значення для вставки: ";
    cin >> value;
    insertAfter(head, target, value);
    printList(head);
    
    // Демонстрація вставки перед заданим елементом
    cout << "\nВставка ПЕРЕД заданим елементом:" << endl;
    cout << "Введіть елемент, перед яким вставити: ";
    cin >> target;
    cout << "Введіть значення для вставки: ";
    cin >> value;
    insertBefore(head, target, value);
    printList(head);
    
    // Очищення пам'яті
    deleteList(head);
    
    return 0;
}
