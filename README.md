#include <iostream>
#include <vector>

using namespace std;

int gcd(int a, int b) {
    while (b != 0) {
        int t = a % b;
        a = b;
        b = t;
    }
    return a;
}

int lcm(vector<int> nums) {
    int result = nums[0];
    for (int i = 1; i < nums.size(); i++) {
        result = lcm(result, nums[i]);
    }
    return result;
}

int main() {
    int p;
    cin >> p;

    vector<int> nums(p);
    for (int i = 0; i < p; i++) {
        cin >> nums[i];
    }

    cout << lcm(nums) << endl;

    return 0;
}
