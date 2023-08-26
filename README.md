import java.util.Scanner;

public class Teststring {
    public static void main(String[] args) throws Exception{
        Scanner scan = new Scanner(System.in);
        System.out.print("Enter expression ");
        String expression = scan.nextLine();
        String[] argument = expression.split("[+\\-*/]");
        if(argument.length !=2) throw new Exception("Must be two operands");
        if(argument[0].trim().length() > 10) throw new Exception("1st operand exceed length !");
        if(argument[1].trim().length() > 10) throw new Exception("2nd operand exceed length !");
        if(argument[0].trim().matches("\\d+")) throw new Exception("1st operand can't be numeral");
        if(argument[1].trim().matches("\\d+") == true){
            int num2 = Integer.parseInt(argument[1].trim());
        if(num2 > 10) throw new Exception("Max numeral 10!");
        }
          if (expression.contains("+")) {
            slozhen(expression);
        } else if (expression.contains("-")) {
            minus(expression);
        } else if (expression.contains("*"))
            umno(expression);
        else if (expression.contains("/")) {
            divid(expression);
        } else System.out.println("No operand");
    }
    public static String slozhen(String expr) {
        String inter = (expr.toString());
        System.out.println(inter.replaceAll("[^\\w]", ""));
        return null;
    }
    public static String minus(String expr) {
        String[] minus = expr.split("[-]");
        String source = (minus[0]);
        String delit = (minus[1]);
        String more = (minus[0]) + minus[1];
        String idea = (more.replaceAll("\"", ""));
        String first = (minus[1]).replaceAll("\"", "");
        System.out.println(idea.replaceAll(first, ""));
        return null;
    }
    public static String umno(String expr) {
        String[] umn = expr.split("[*]");
        String source = (umn[0]);
        String delit = (umn[1]);
        String delit1 = delit.trim();
        int counter = Integer.parseInt(delit1);
        String idea = (source.replaceAll("\"", ""));
        String idea1 = ((idea.repeat(counter)));
        String resul = (idea1.replaceAll("\\s", ""));
        if (resul.length()>40){
            System.out.println(resul.substring(0,40) + "...");
        }
        else System.out.println(resul);
        return null;
    }
    public static String divid(String expr) {
        String[] delen = expr.split("[/]");
        String source = (delen[0]);
        String delit = (delen[1]);
        String delit1 = delit.trim();
        int counter = Integer.parseInt(delit1);
        String idea = (source.replaceAll("\"",""));
        String idea1 = idea.trim();
        int length = idea1.length();
        int res = length/counter;
        System.out.println(idea1.substring(0,res));
        return null;
    }
}
