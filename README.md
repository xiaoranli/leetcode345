# 24、leetcode345. 反转字符串中的元音字母
解法一：
--  
思路：
--
    
代码： 
--
<pre>
/**
 * @author lihe
 * @date 2019/10/19 19:17
 * @descriptor
 */
public class ReverseVowels_345 {
    public static String reverseVowels(String s) {
        String str = "aeiouAEIOU";
        char[] chars = s.toCharArray();
        int i = 0,j = s.length() - 1;
        while(i < j){
            if(str.contains(String.valueOf(chars[i])) && str.contains(String.valueOf(chars[j]))){
                swap(chars,i++,j--);
            }else if(str.contains(String.valueOf(chars[i]))){
                j--;
            }else if(str.contains(String.valueOf(chars[j]))){
                i++;
            }else{
                i++;
                j--;
            }
        }
        return new String(chars);
    }
    private static void swap(char[] c, int i, int j) {
        char ch = c[i];
        c[i] = c[j];
        c[j] = ch;
    }
    public static void main(String[] args) {
        String s = "leetcode";
        String s1 = reverseVowels(s);
        System.out.println(s1);
    }
}
</pre>
