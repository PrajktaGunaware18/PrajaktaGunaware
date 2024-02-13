package Abstractclass;

import java.util.*;

abstract class value {
	int base, index;
	int p = 1;
	int digit;
	int key;

	void setvalue(int base, int index) {

		this.base = base;
		this.index = index;

	}

	void setNumber(int no, int searchkey) {
		digit = no;
		key = searchkey;
	}

	abstract int getResult();

}

class Power extends value {

	int getResult() {

		for (int i = 1; i <= index; i++) {
			p = p * base;

		}
		return p;

	}

}

class SearchDigit extends value {
	

	int getResult() {
		int rem;


		while (digit > 0)// 12
		{
			rem =digit%10;// 2
			if (rem ==key) {
				return key;
			
			}
			digit=digit/10;

		}
		
			return -1;
		
		
	}
}

public class Abstractclassvalue {

	public static void main(String[] args) {

		Scanner sc = new Scanner(System.in);

		System.out.println("Enter the base and index");

		int base = sc.nextInt();

		int index = sc.nextInt();
		System.out.println("Enter the number");

		int no = sc.nextInt();

		Power po = new Power();
		po.setvalue(base, index);

		int r = po.getResult();
		System.out.println("Enter the serach number\n");
		int searchkey = sc.nextInt();

		System.out.println("Result is" + r);
		SearchDigit sd = new SearchDigit();
		sd.setNumber(no, searchkey);
		int result = sd.getResult();
		if(result==-1)
		{
			System.out.println("Digit not found in the number");
		}
		else
		{
		System.out.println("Digit is found:"+result);
	}
}
}
