# DSA-Journey
My goal to grasp the opportunities and build up the problem solving skills looking different world problems
Rishabh Sindhwal
LeetCode ID: srishu2006

problem statement - Given an array of intervals where intervals[i] = [starti, endi], merge all overlapping intervals, and return an array of the non-overlapping intervals that cover all the intervals in the input.

 solution -     vector<vector<int>> merge(vector<vector<int>>& intervals) {
      int n = intervals.size();
      sort(intervals.begin(),intervals.end());
      vector<vector<int>>ans;
      for(int i=0; i<n; i++)
      {
        int start = intervals[i][0];
        int end = intervals[i][1];
        if(ans.empty() || intervals[i][0]>ans.back()[1])
        {
            ans.push_back(intervals[i]);
        }
        else 
        {
           ans.back()[1] = max(ans.back()[1],intervals[i][1]);
        }
      }
      return ans;
    }
