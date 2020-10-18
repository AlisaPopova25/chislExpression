# chislExpression
import java.util.Scanner;
public class Main{
	public static void main(String[] args) {
	    Scanner in = new Scanner(System.in);
		String vvod = in.nextLine();          //получаем на ввод строку с выражением
		char[] array = vvod.toCharArray();    //преобразуем строку в массив символов char
		int d = 0;               //индекс знака
		String str1 = "";        //переменная, где будет храниться число перед знаком
		String str2 = "";        //переменная, где будет храниться число после знака
		for(int i = 0; i<array.length; i++){       //перебираем все индексы
		    if (array[i]=='*'|| array[i]=='/' || array[i]=='+'||array[i]=='-'){  //если символ с текущим индексом равен знаку действия
		        d = i;    //фиксируем индекс знака действия
		    }
		}
		for (int j = 0; j < d; j++) {    //перебираем индексы цифр перед знаком
                str1 += array[j];    //складываем в строку1 все цифры перед знаком действия
		    }
		for (int g = d+1; g < array.length; g++) {   //перебираем индексы цифр после знаком
                str2 += array[g];                //складываем в строку2 все цифры после знака действия
		}
		int chisl1 = Integer.parseInt(str1);   //преобразуем строку1 в число1
		int chisl2 = Integer.parseInt(str2);   //преобразуем строку2 в число2
		if (array[d]=='+'){                    //выполняем действие с числами в зависимости от знака и выводим результат
		    System.out.println(chisl1+chisl2);
		}
	    else if (array[d]=='-'){
		    System.out.println(chisl1-chisl2);
		}
		else if (array[d]=='*'){
		    System.out.println(chisl1*chisl2);
		}
		else if (array[d]=='/'){
		    System.out.println(chisl1/chisl2);
		}
	}
}
