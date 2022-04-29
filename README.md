# RomanToInteger.java

class Solution1 {
    HashMap<Character, Integer> dic = new HashMap<>();
    public int romanToInt(String s) {
        dic.put('I',1);
        dic.put('V',5);
        dic.put('X',10);
        dic.put('L',50);
        dic.put('C',100);
        dic.put('D',500);
        dic.put('M',1000);
        int n = 0;
        int present = 0, upcoming = dic.get(s.charAt(0));
        for(int i=0; i<s.length()-1; i++){
            present = dic.get(s.charAt(i));
            upcoming = dic.get(s.charAt(i+1));
            if(present<upcoming){
                n-=present;
            }else{
                n+=present;
            }
        }
        n+=upcoming;
        return n;
    }
}
