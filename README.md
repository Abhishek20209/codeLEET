# codeLEET
1351. Count Negative Numbers in a Sorted Matrix
class Solution {
public:
    int countNegatives(vector<vector<int>>& grid) {
        
        int cnt=0,mid=0;
        for(auto it:grid){
            int i=0,j=it.size()-1;
            if(it[0]<0)
            {
                cnt=cnt+j+1;
            }
            else if(it[j]>0)
            {
                cnt=cnt+0;
            }
            else{
                while(i<=j)
                {
                    mid=(i+j)/2;
                    if(it[mid]<0&&it[mid-1]>=0)
                    {
                        cnt=cnt+(it.size()-mid);
                        break;
                    }
                    else if(it[mid]<0)
                    {
                        j=mid-1;
                    }
                    else
                    {
                        i=mid+1;
                    }
                }
            }
        }
        return cnt;
    }
};
