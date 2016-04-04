# Snowluck
coding practice with dynamic programming
README for the pseudo
coded in java

> read inputs and put the information into a 2d array, where treeInfo[i] stores the information of Tree i
  > treeInfo[i][0] = Tree the scout is heading to if he fails to hit the target of Tree i
  > treeInfo[i][1] = distance from Tree i to the Tree of treeInfo[i][0]

  > treeInfo[i][2] = Tree the scout is heading to if he hits the target of Tree i
  > treeInfo[i][3] = distance from Tree i to the Tree of treeInfo[i][2]
> use dynamic programming (3d array) to calculate the minimum distance a scout travels to the desired tree with j number of bulls eye
  (0 <= j <= number of trees)
  > set dp[0][1][0] to 0, other elements to -1 
  > for n = (1 to numTrees^2 ) //number of shots fire
    > for m = ( 1 to numTrees-1 ) //current location of the scout after firing n shots
      > for k = ( 0 to numTrees ) //number of bulls eye made
        > if dp[n][m][k] is visited (not -1)
          > update dp[n+1][treeInfo[m][2]][k+1] and dp[n+1][treeInfo[m][0]][k] (for bulls eye and miss, respectively)
          
  > search for the lowest value of dp[i][numTrees][j] for each j (number of bulls eye made), varying the number of i (shots fired)
  > print result in desired format
  
Summary: run time and memory: O(n^4) //it may be possible to use a 2d array for dynamic programming to achieve the same result.
