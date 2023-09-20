# Sets-algorithm
# This is a C++ code written to find a given set's union, the intersection, and the subtraction.
# Oluwatobiloba Lawuyi
# 17th of September, 2023
# Discrete Math Homework 1

#include <iostream>
#include <vector>
#include <algorithm>

std::vector<int> unionSet(const std::vector<int>& A, const std::vector<int>& B) {
    std::vector<int> result = A;
    for (int element : B) {
        if (std::find(result.begin(), result.end(), element) == result.end()) {
            result.push_back(element);
        }
    }
    return result;
}


std::vector<int> intersectionSet(const std::vector<int>& A, const std::vector<int>& B) {
    std::vector<int> result;
    for (int element : A) {
        if (std::find(B.begin(), B.end(), element) != B.end()) {
            result.push_back(element);
        }
    }
    return result;
}

std::vector<int> setDifference(const std::vector<int>& A, const std::vector<int>& B) {
    std::vector<int> result;
    for (int element : A) {
        if (std::find(B.begin(), B.end(), element) == B.end()) {
            result.push_back(element);
        }
    }
    return result;
}

int main(){
    std::vector<int> A = {4, 6, 7, 8, 9, 12, 1, 3, 9, 77};
    std::vector<int> B = {3, 5, 22, 10, 8, 7, 6, 69, 4, 1};

    

    std::vector<int> resultUnion = unionSet(A, B);
    std::cout << "A U B: {";
    for(int element: resultUnion){
        std:: cout << element << " ";
    }
    std::cout << "}" << std:: endl;

    std::vector<int> resultIntersect = intersectionSet(A, B);
    std::cout << "A n B: {";
    for(int element: resultIntersect){
        std::cout << element << " ";
    }
    std::cout << "}" << std::endl;

    std::vector<int> difference = setDifference(A, B);
    std::cout << "A - B: {";
    for(int element: difference){
        std::cout << element << " ";    }
    std::cout << "}" << std::endl;


    return 0;
}
