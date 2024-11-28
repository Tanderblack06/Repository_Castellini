import java.util.Scanner;
import java.util.ArrayList; // per una array di cavalli
import java.util.List;


public class GaraCavalli {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.print("inserisci l'intero percorso per la gara dei cavalli: ");
        int percorsoTotale = input.nextInt();
        input.nextLine();

        List<Cavallo> cavalli = new ArrayList<>();
        System.out.print("Inserire il numero di cavalli in gara: ");
        int numeroCavalli = input.nextInt();
        input.nextLine();

        for(int i =0; i<numeroCavalli; i++){
            System.out.print("inserisci il nome del cavallo numero "+(i+1)+" :");
            String namecavallo = input.nextLine();
            cavalli.add(new Cavallo(namecavallo, percorsoTotale));
        }
        input.close();

        System.out.println("LA GARA E INIZIATA");

        for(Cavallo cavallo: cavalli){   //start
            cavallo.start();
        }

        for(Cavallo cavallo: cavalli){
            try {
                cavallo.join(); //Attende il completamento del thread "cavallo"
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
        System.out.println("\n LA GARA E TERMINATA");
    }
}
