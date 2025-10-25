import java.util.*;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner=new Scanner(System.in);
        List<Client> PR_INFO =new LinkedList<>();

        System.out.println("*****************************");
        System.out.print("how many client do you enter: ");
        int n= scanner.nextInt();
        scanner.nextLine();

        for (int i=1; i<=n ; i++){

            System.out.println("_____ N:"+ i +" client_____");


            long id;
            while(true) {

                System.out.print("personal id : ");
                id= scanner.nextLong();
                scanner.nextLine();

                if (String.valueOf(id).length()==11 ) {
                    break;
                }else {
                    System.out.println("personal id must be 11 number ! ❌ ");
                }

            }

            System.out.print("client name : ");
            String name=scanner.nextLine();


            System.out.print("client lastname : ");
            String Lname=scanner.nextLine();

            System.out.print("client gmail : ");
            String jmail=scanner.nextLine();

            String IBAN= new accounts().iban(i);
            
            PR_INFO.add(new Client(i,id,name,Lname,jmail,IBAN));

        }

        for(Client data : PR_INFO ){
            System.out.println("________________________________________________");
            System.out.println(data.toString());
        }

    }
}

