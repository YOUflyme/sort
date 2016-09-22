# sort
four methods of sorting

import java.util.Scanner;

public class SortTest {
	public static void main(String[] args)
	{
		Scanner in = new Scanner(System.in);
		
		int[] num = new int[10];
		System.out.println("请输入10个整数。");
		for(int i = 0; i < 10; i++)
		{
			System.out.printf("请输入第%d个整数。", i + 1);
			num[i] = in.nextInt();
		}
		
		System.out.println("排序前： ");
		for(int i = 0;  i< 10; i++)
			System.out.print(num[i] + "  ");
		
		System.out.println();
//		num = BubbleSort(num);
//		num = ChoiceSort(num);
//		num = InsertSort(num);
		num = QuickSort(num, 0, 9);
	
		System.out.println("排序后：");
		for(int i = 0; i < 10; i++)
			System.out.print(num[i] + "  ");
		
		System.out.println();
	}
	
	private static int[] QuickSort(int[] num, int low, int high)
	{
/**		int r1, r2, r3;
		r1 = (int)Math.random() * 9;
		r2 = (int)Math.random() * 9;
		r3 = (int)Math.random() * 9;
		int temp = (r1 + r2 + r3) / 3;
*/
		int i = low, j = high;
		int temp = num[i];
		if(low < high)
		{
		while(i < j)
		{
			while((num[j] >= temp) && (i < j))
			{
				j--;
			}
			num[i] = num[j];
			while((num[i] <= temp) && (i < j))
			{
				i++;
			}
			num[j] = num[i];
		}
		num[i] = temp;
		QuickSort(num, low, i - 1);
		QuickSort(num, j + 1, high);
		}
		return num;
	}
/**	
	private static int[] InsertSort(int[] num)
	{
		for(int i = 1; i < 10; i++)
		{
			int temp = num[i];
			for(int j = i; j > 0; j--)
			{
				if(num[j - 1] > temp)
				{
					num[j] = num[j - 1];
					num[j - 1] = temp;
				}
			}
		}
		return num;
	}*/
	/**
	private static int[] ChoiceSort(int[] num)
	{
		for(int i = 0; i < 9; i++)
		{
			int min = i;
			int j;
			for(j = i + 1; j < 10; j++)
			{
				if(num[min] > num[j])
				{
					min = j;
				}
			}
			if(min != i)
			{
				int temp = num[i];
				num[i] = num[min];
				num[min] = temp;
			}
		}
		return num;
	}*/
/**
	private static int[] BubbleSort(int[] num) {
		// TODO Auto-generated method stub
		for(int i = 0; i < 9; i++)
		{
			for(int j = i + 1; j < 10; j++)
			{
				if(num[i] > num[j])
				{
					int temp = num[i];
					num[i] = num[j];
					num[j] = temp;
				}
			}
		}
		return num;
	}
*/
}
