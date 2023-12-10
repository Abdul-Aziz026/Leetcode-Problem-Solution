# Leetcode-Problem-Solution


class Solution {
public:
    int bigmod(int a, int p, int m) {
        int ans = 1 ;
        while (p > 0) {
            if (p & 1) {
                ans = (ans * a) % m ;
            }
            a = (a * a) % m ;
            p >>= 1 ;
        }
        return ans ;
    }
    vector<int> getGoodIndices(vector<vector<int>>& variables, int target) {
        int idx = 0;
        vector <int> ans;
        for (auto a: variables) {
            int x = bigmod(bigmod(a[0], a[1], 10), a[2], a[3]);
            if (x == target) ans.push_back(idx);
            ++idx;
        }
        return ans;
    }
};
