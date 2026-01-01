class Solution {
public:
    int maxArea(vector<int>& height) {
        int l = 0;
        int r = height.size() - 1;
        int ans = 0;
        while (l < r) {
            int w = r - l;
            int cap = min(height[l], height[r]);
            ans = max(ans, w * cap);
            (height[l] < height[r]) ? l++ : r--;
        }
        return ans;
    }
};