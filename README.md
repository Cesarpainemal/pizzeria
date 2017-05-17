# pizzeria
import java.util.Scanner;

/**
 *
 * @author User
 */
public class Pizzeria {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {

        double queso = 0;
        double base_de_pizza = 0;
        double jamon = 0;
        double tomate = 0;
        double champiñones = 0;
        double gastos = 0, ganancias = 0;
        boolean consulta = false;
        int pizzas_vendidas = 0;
        int[] precio = new int[50];
        String[] tipo_pizza = new String[50];

        Scanner entrada = new Scanner(System.in);

        while (consulta == false) {

            System.out.println("¿Cuanto queso se compro?");
            queso = entrada.nextInt();
            while (queso < 10 || queso > 20) {
                System.out.println("cantidad invalida ingrese nuevamente");
                queso = entrada.nextInt();
            }
            gastos = queso * 5000;

            System.out.println("¿Cuantas unidades de pizza se compro?");
            base_de_pizza = entrada.nextInt();
            while (base_de_pizza < 2 || base_de_pizza > 50) {
                System.out.println("cantidad invalida ingrese nuevamente");
                base_de_pizza = entrada.nextInt();

            }

            gastos = gastos + base_de_pizza * 500;

            System.out.println("Â¿Cuanto jamon se compro?");
            jamon = entrada.nextInt();
            while (jamon < 5 || jamon > 10) {
                System.out.println("cantidad invalida ingrese nuevamente");
                jamon = entrada.nextInt();
            }
            gastos = gastos + jamon * 2500;

            System.out.println("Â¿Cuanto tomate se compro?");
            tomate = entrada.nextInt();
            while (tomate < 10 || tomate > 15) {
                System.out.println("cantidad invalida ingrese nuevamente");
                tomate = entrada.nextInt();
            }

            gastos = gastos + tomate * 900;

            System.out.println("Â¿Cuantos champiÃ±ones se compro?");
            champiñones = entrada.nextInt();
            while (champiñones < 5 || champiñones > 10) {
                System.out.println("cantidad invalida ingrese nuevamente");
                champiñones = entrada.nextInt();
            }
            gastos = gastos + champiñones * 3500;

            consulta = true;

        }
        int i = 0;
        int opcion=0;
        while (opcion != 5) {
            System.out.println("Que tipo de pizza: \n"
                    + "[1] pizza 1\n"
                    + "[2] pizza 2\n"
                    + "[3] pizza3\n"
                    + "[4] imprimir informe del dia\n"
                    + "[5] finalizar\n");

            opcion = entrada.nextInt();

            switch (opcion) {
                case 1:
                    if (base_de_pizza >= 1 && queso >= 0.1
                            && tomate >= 0.2 && jamon >= 0.1) {

                        base_de_pizza--;
                        queso -= 0.1;
                        tomate -= 0.2;
                        jamon -= 0.1;
                        ganancias += 2500;
                        precio[i] = 2500;
                        tipo_pizza[i] = "pizza tipo 1";
                        pizzas_vendidas++;
                        i++;
                    } else {
                        System.out.println("No queda hermano");
                    }
                break;

                case 2:
                    if (base_de_pizza >= 1 && queso >= 0.2
                            && tomate >= 0.2 && champiñones >= 0.1) {

                        base_de_pizza--;
                        queso -= 0.2;
                        tomate -= 0.2;
                        champiñones -= 0.1;
                        ganancias += 3000;
                        precio[i] = 3000;
                        tipo_pizza[i] = "pizza tipo 2";
                        pizzas_vendidas++;
                        i++;
                    } else {
                        System.out.println("No queda hermano");
                    }
                break;
                case 3:

                    if (base_de_pizza >= 1 && queso >= 0.2
                            && champiñones >= 0.2 && jamon >= 0.2) {

                        base_de_pizza--;
                        queso -= 0.2;
                        champiñones -= 0.2;
                        jamon -= 0.2;
                        ganancias += 3500;
                        precio[i] = 3500;
                        tipo_pizza[i] = "pizza tipo 3";
                        pizzas_vendidas++;
                        i++;
                    } else {
                        System.out.println("No queda hermano");
                    }
                break;
                case 4:
                    for (i = 0; i < pizzas_vendidas; i++) {
                        System.out.println(tipo_pizza[i]+" "+precio[i]);
            
                    }
                case 5:
                    break;
                default:

                    System.out.println("opcion ingresa erronea");
                break;
            }

        }
        
    }
}
