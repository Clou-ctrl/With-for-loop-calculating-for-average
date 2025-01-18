// With-for-loop-calculating-for-average
#include <iostream>
#include <vector>
#include <string>

using namespace std;

struct Breed {
    string name;
    vector<int> types;
    double averageGrade;
};

double calculateAverage(const vector<int>& types) {
    int total = 0;
    for (int type : types) {
        total += type;
    }
    return types.empty() ? 0 : static_cast<double>(total) / types.size();
}

int main() {
    vector<Breed> breeds;
    int numBreeds;

    cout << "Enter the number of breeds: ";
    cin >> numBreeds;

    for (int i = 0; i < numBreeds; i++) {
        Breed breed;
        int numTypes;

        cout << "\nEnter name of the breed " << i + 1 << ": ";
        cin.ignore(); // Clear input buffer
        getline(cin, breed.name);

        cout << "Enter the number types of " << breed.name << ": ";
        cin >> numTypes;

        cout << "Enter their average number: ";
        
            int type;
            cin >> type;
            breed.types.push_back(type);
        

        breed.averageGrade = calculateAverage(breed.types);

        breeds.push_back(breed);
        
    }
    
    cout << "\nAverage Report:\n";
    cout << "-----------------------\n";
    for (const auto& breed : breeds) {
        cout << "Breed: " << breed.name << "\n";
        cout << "Types number: ";
        for (int type : breed.types) {
            cout << type << " ";
        }
        cout << "\nAverage: " << breed.averageGrade << "\n\n";
    }

    return 0;
}
