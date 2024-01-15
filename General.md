### List & Stack & Queue
> PriorityQueue<obj,int>(heap), Dictionary, List, Stack, Queue, HashSet 

### Binary Search
> Keywords: Sorted, Half Sorted, Minimum, Maximum
```csharp
public int LowerBound(int[] nums, int target){
    Array.Sort(nums,(x,y)=>{return x.CompareTo(y)}); //y.CompareTo(x) desc

    int left=0, right=nums.Length-1;
    while (left<=right){
        int mid= left + (right-left)/2;
        
        //Logic on compare left & right in half sorted array
        //Then determine left or right side
        if(nums[mid]<target){
            left=mid+1;
        }else{
            right=mid-1;
        }
    }

    return left;
}
```

### Two Pointers & Sliding Window
> Keywords: Sub-Array, Monotonicity-Right pointer never go back 
```csharp
public int RightSliding(int[] nums){
    int result=int.MinValue;
    int extraInfo=0; //middle information for maintain
    int left=0; //sliding pointer
    
    for(var right=0;right<nums.Length;right++){
        extraInfo+=nums[right];

        while(extraInfo) //break the extraInfo when false
        {
            left+=1;
        }

        result=Math.Max(result,right-left);
    }
}

public int() LeftRightSliding(int[] nums, int target){
    int left=0;
    int right=nums.Length-1;
    //in a sorted array
    while(left<right){
        var info=nums[left]+nums[right];
        if(target==info){
            return (left+1,right+1)
        }

        if(info<target){
            left++;
        }else{ //greater than target
            right++;
        }
    }

    return ();
}
```

### DFS
```csharp
public int Dfs(TreeNode node){
    if(node==null) return 0; //beyond leaf

    if (==) {//logic on equal or not equal case
        Dfs() //only call one side
    }

    return 1  + Math.Max(Dfs(node.left),Dfs(node.right));
}
```

### BFS
```csharp
public int Bfs(int[][] grids){
    var rowLength=grid.Length;
    var colLength=grid[0].Length;
    var steps=new int[]{new[]{1,0},new[]{-1,0},new[]{0,1},new[]{0,-1}};
    var visited=new Dictionary<(int,int),int>(); //save time
    var queue=new Queue<(int,int)>();
    
    queue.Enqueue((0,0)); //add first item
    while(queue.Count>0){
        (int x,int y)=q.Dequeue();
        visited.Add((step[0],step[1]),true);
        foreach(var step in steps){
            if()//conditions on not beyond boundaries
            {
                visited.Add((step[0],step[1]),true);
                queue.Enqueue(newCords);
            }else{ //visited already
                //other logic
            }
        }
    }
}

```



### PreFix Sum
> Keywords: Sum on an sub-array range
```csharp
public int[] PrefixSum(int[] nums)
{
    int n = nums.Length;
    int[] sum = new int[n + 1]; //array for store calculated values
    for (int i = 1; i <= n; i++)
    {
        sum[i] = sum[i - 1] + nums[i - 1]; //adding previous two numbers
    }
    return sum;
}
```
