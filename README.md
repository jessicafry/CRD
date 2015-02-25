# Cosmic-Ray-Detector
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.lang.reflect.Array;
import java.util.ArrayList;
import java.util.Scanner;

/****************************************************************
 * 1. Read in text file
 * 2. Extract each new line
 * 3. Save 16 Words
 * 4. Analyze
 * 
 * @author Jessica and Simran
 ****************************************************************/

public class readData 
{
	final static Scanner CONSOLE = new Scanner(System.in);
	final static String TEXT = "Test_2.log"; //text file is CRD.txt
	final static int NUMWORDS = 16;
	static ArrayList<String[]> paragraph = new ArrayList<String[]>();
	static ArrayList<Integer[]> btparagraph = new ArrayList<Integer[]>();
	public static void main(String[] args) 
	{
		readIn();
		convertBaseTen();
	}

	/***
	 * Scan in new lines of the text file
	 */
	public static void readIn()
	{
		Scanner s = null;
		try
		{
			s = new Scanner(new BufferedReader(new FileReader(TEXT)));
			String nextLine = s.nextLine();
			while(nextLine != null)
			{
				WordExtractor(nextLine);
				System.out.println("Got line?");
			}
		}
		catch (IOException e)
		{	
			System.out.println("oops");
		}
	}
	public static void WordExtractor(String line)
	{
		String[] sentence = new String[16];
		for(int n = 0; n<NUMWORDS; n++)
		{
			int end = line.indexOf(" ");
			String word = line.substring(0, end+1);
			line = line.substring(end+1);
			sentence[n] = word;
		}
		paragraph.add(sentence);
	}	
	
	public static void convertBaseTen()
	{
		for(int i = 0; i < paragraph.size(); i ++)
		{
			String[] sentence = paragraph.get(i);
			Integer[] btsetence = new Integer[16];
			for(int j = 0; j < sentence.length; j ++)
			{
				String word = sentence[j];
				int value = 0;
				for(int k = word.length(); k > -1; k--)
				{
					char character = word.charAt(k);
					int amount = determineAmount(character, word, k);
					value += amount;
				}
				btsetence[j] = value;
			}
			btparagraph.add(btsetence);
		}
	}
	public static int determineAmount(char character, String word, int k)
	{
		int amount = 0;
		if(character == '0')
		{
			amount = 0;
		}
		if(character == '1')
		{
			amount = 1;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == '2')
		{
			amount = 2;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == '3')
		{
			amount = 3;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == '4')
		{
			amount = 4;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == '5')
		{
			amount = 5;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == '6')
		{
			amount = 6;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == '7')
		{
			amount = 7;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == '8')
		{
			amount = 8;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == '9')
		{
			amount = 9;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == 'A')
		{
			amount = 10;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == 'B')
		{
			amount = 11;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == 'C')
		{
			amount = 12;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == 'D')
		{
			amount = 13;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == 'E')
		{
			amount = 14;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		if(character == 'F')
		{
			amount = 15;
			for(int l = word.length() - k; l > 0; l--)
			{
				amount = amount * 16;
			}
		}
		return amount;
	}
	
	
}
