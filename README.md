<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=190&section=header&text=Sumit%20Kumar&fontSize=40&fontColor=ffffff&animation=fadeIn" />

<!-- <h1 align="center">Hi 👋, I'm Sumit Kumar</h1> -->

<p align="center">
 <img src="https://readme-typing-svg.herokuapp.com?lines=Welcome+to+my+GitHub+Profile;Aspiring+Full+Stack+Web+Developer;Frontend+Developer;Backend+Developer;Building+Responsive+Web+Projects&center=true&width=500&height=45">
</p>

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=120&section=footer" alt="Footer Wave" />
</div>

<!-- Hi, i am from **dhanbad jharkhand**, i have done my **schooling** from **dhanbad jharkhand**, now i am here to complete my **graduation** in **computer science branch** from **sec sasaram engineering college**, my **goal & achievements** is i will became a good software developer in **future**.-->

<!-- <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f0c29,50:302b63,100:24243e&height=190&section=header&text=Sumit%20Kumar&fontSize=40&fontColor=ffffff&animation=twinkling" /> --> 

# Here are the commit list 

- 4th commit list
- 5th commit is the class solution
- 6th commit is the preview list
- 7th commit is the last commit for today

---

 class Solution {
public:
    int minMoves(vector<int>& nums, int limit) {
        int n = nums.size();

        // difference array
        vector<int> diff(2 * limit + 2, 0);

        int a,b,low,high,sum;
        for(int i = 0; i < n / 2; i++) {
            a = nums[i];
            b = nums[n - 1 - i];

            low = min(a, b) + 1;
            high = max(a, b) + limit;

            sum = a + b;

            // initially all sums need 2 moves
            diff[2] += 2;
            diff[2 * limit + 1] -= 2;

            // one move range
            diff[low] -= 1;
            diff[high + 1] += 1;

            // exact sum needs 0 move
            diff[sum] -= 1;
            diff[sum + 1] += 1;
        }

        int ans = INT_MAX;
        int moves = 0;

        // calculate prefix sum
        for(int target = 2; target <= 2 * limit; target++) {
            moves += diff[target];
            ans = min(ans, moves);
        }
        return ans;
    }
};
