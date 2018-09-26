```java
package com.mengfansheng;

import java.util.Arrays;

//递归解决N皇后问题
public class Recursion {
	public static void main(String[] args) {
		Nqueen(0, new int[4]);
	}
	public static void  Nqueen(int k, int[] queenPos){
		int i;
		int N = queenPos.length;
		if(k == N){ //N个皇后已经摆好
			System.out.println(Arrays.toString(queenPos));
			return;
		}
		for( i = 0; i < N; i++){ // 逐个尝试第k个皇后放在哪一列
			int j = 0;
			//每尝试一列就要和前面的k-1个皇后比较下有没有冲突的
			for(j = 0; j < k; j++){	
				if(queenPos[j] == i || Math.abs(queenPos[j] - i) == Math.abs(k - j)){
					break;//冲突，说明摆在第i列不行，测试下一列位置
				}
			}
			if(j == k){
				queenPos[k] = i;
				Nqueen(k+1, queenPos);
			}
		}
	}
}

```

