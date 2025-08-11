class Solution:
    def findLHS(self, nums: List[int]) -> int:
        
        count = Counter(nums)
        mx = 0
        
        for num in count:
            if num + 1 in count:
                mx = max(mx, count[num] + count[num + 1])
        
        return mx