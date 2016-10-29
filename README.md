1.Length of Longest Palindrome that can be built from letters
public int longestPalindrome(String s){		
		int rt = s.length()-1, lt;
		int max = 1, maxtemp, lttemp, rttemp;
		
		while(rt>=0){		
					
			lt = rt - 1;
			maxtemp = 0;
			lttemp = lt;
			rttemp = rt;
			while(rttemp<s.length()&&lttemp>=0){				
				if(s.charAt(lttemp)==s.charAt(rttemp)){
					lttemp--;
					rttemp++;
					maxtemp+=2;	
				}else{
					break;
				}			
			}
			
			if(maxtemp>max)
				max = maxtemp;
						
			lt = rt - 2;
			maxtemp = 1;
			lttemp = lt;
			rttemp = rt;
			while(rttemp<s.length()&&lttemp>=0){				
				if(s.charAt(lttemp)==s.charAt(rttemp)){
					lttemp--;
					rttemp++;
					maxtemp+=2;	
				}else{
					break;
				}			
			}
			
			if(maxtemp>max)
				max = maxtemp;
			
			rt--;	
			
		}
		return max;
		
	}
	
	
}


2.Algorithm to find maximum stock profit
    public int maxProfit(int[] prices) {
        if(prices == null || prices.length ==0){
            return 0;
        }
        int sum = 0;
        for(int i = 1; i < prices.length; i++){
            if(prices[i - 1] < Prices[i]){
                sum = sum + prices[i] - prices[i - 1];
            }
        }
        return sum;
    }
}


3.Given a column number in Excel, return corresponding column number
public class Solution {
    public int titleToNumber(String str) {
        if(str == null || str.length() == 0){
            return 0;
        }
        int sum = 0;
        int current = 1;
        for(int i = str.length() - 1; i >= 0 ;i--){
            sum = sum + (str.charAt(i) - 'A' + 1) * current;
            current=current* 26;
        }
        return sum;
    }
}

