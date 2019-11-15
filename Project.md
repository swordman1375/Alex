package тестовое.задание2_it.lab.epol.soft;

import java.util.Scanner;

public class ТестовоеЗадание2_ITLABEpolSoft {

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.println("Введите первый массив: ");
        String str1 = in.nextLine();
        System.out.println("Введите второй массив: ");
        String str2 = in.nextLine();
        in.close();
        String newstr1 = removeCharAt(str1, str1.length() - 1);
        String newstr2 = removeCharAt(str2, str2.length() - 1);
        String delims1 = ",";
        String[] Parsestr1 = newstr1.split(delims1);
        String[] Parsestr2 = newstr2.split(delims1);
        for (int i = 0; i < Parsestr1.length; i++) {
            boolean b = check(Parsestr1[i], Parsestr2);
            if (b) {
                System.out.print("1");
            } else {
                System.out.print("0");
            }

        }

    }

    static boolean check(String s, String[] r) {
        boolean a = false;
        for (int i = 0; i < r.length; i++) {
            if (s.equals(r[i])) {
                a = true;
            }
        }
        return a;
    }

    private static String removeCharAt(String s, int pos) {
        return s.substring(1, pos);
    }

}
