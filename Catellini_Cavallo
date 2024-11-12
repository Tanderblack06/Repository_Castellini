import java.util.Random;

public class Cavallo extends Thread {

    private String name ;
    private int metriTot;
    private int metriStart = 0;
    private static volatile boolean raceOver = false;
    Random rand = new Random();

    public Cavallo(String name, int metriTot){
        this.name = name;
        this.metriTot=  metriTot;
    }

    @Override
    public void run() {
        // crea radomico numero tra 0 e 9
       while(metriStart<metriTot){

           if (raceOver) {
               System.out.println("Il cavallo " + name + " si ferma perché la gara è già finita.");
               return;
           }
           int percorsofatto = rand.nextInt(10)+1; // avvrei usato anche (int)(Math.random(10)+1);
           metriStart += percorsofatto;

           // check del valore
           if (metriStart >= metriTot) {
               metriStart = metriTot;
               if (!raceOver) { // If race is not over, this horse is the winner
                   raceOver = true;
                   System.out.println("Il cavallo " + name + " è arrivato primo al traguardo!");
               }
               break;
           }


           System.out.println("il cavallo: "+ this.name+" ha percorso: "+ metriStart);
           try{
               Thread.sleep(300); // aspetta 3ms per rifare il ciclo while
           }catch (InterruptedException e){
               e.printStackTrace(); // mi dice  dove si trovera l'eventuale errore
           }
       }
    }
}
