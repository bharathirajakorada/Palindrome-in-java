# Palindrome-in-java
An advanced level palindrome, to check a phrase or sentence containing alphabets and special character is a palindrome or not 

public class Palindrome {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		// it should handle mixed case alphabets
		String text = "AbutTuba";
		isPalindrome(text);

		// DO NOT MODIFY BELOW TEST CASES
		isPalindrome("A but tuba.");
		isPalindrome("A car, a man, a maraca.");
		isPalindrome("A Toyota! Race fast, safe car! A Toyota!");
		isPalindrome("");
	}

	public static void isPalindrome(String str) {
		char[] strArray = str.toCharArray();
		int lastIndex = strArray.length - 1;
		char[] str1Array = new char[lastIndex + 1];

		int index1 = 0, index2 = 0;
		for (index1 = 0; index1 <= lastIndex; index1++) {
			if (strArray[index1] >= 'A' && strArray[index1] <= 'Z'
					|| strArray[index1] >= 'a' && strArray[index1] <= 'z')
				str1Array[index2++] = strArray[index1];
		}

		int newLastIndex = index2 - 1;
		int firstIndex = 0;

		while(newLastIndex > firstIndex) {
			if(lowerCheck(str1Array[firstIndex++]) != lowerCheck(str1Array[newLastIndex--]))
			{
				System.out.println("Not a palindrome");
				return;
			}
		}
		System.out.println("Is a palindrome");
	}
	public static char lowerCheck(char alphabet) {
		if (alphabet >= 'A' && alphabet <= 'Z')
			return (char) ((char) alphabet + 32);
		return alphabet;
	}

}
