/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Main.java to edit this template
 */
package aqui_estan_los_18_ejercicios;

import java.util.Scanner;

/**
 *
 * @author Andrew
 */
public class Aqui_estan_los_18_ejercicios {

    /**
     * @param palabra
     * @return
     * @paramargs the command line arguments
     *
     *
     */
    public static boolean esPalindromo(String palabra) {
        // Eliminar espacios y convertir a minúsculas
        String palabraLimpia = palabra.replaceAll("[^a-zA-Z0-9]", "").toLowerCase();

        // Invertir la palabra
        String reverso = new StringBuilder(palabraLimpia).reverse().toString();

        // Comparar
        return palabraLimpia.equals(reverso);
    }

    private static boolean esCapicua(long numero) {
        long original = numero;
        long invertido = 0;

        while (numero > 0) {
            long digito = numero % 10;
            invertido = invertido * 10 + digito;
            numero /= 10;
        }

        return original == invertido;
    }

    public static void main(String[] args) {
        // Datos del login
        String usuario = "cami";
        String paso = "1234";

        Scanner escaner = new Scanner(System.in);

        while (true) {
            System.out.println("Inserte usuario:");
            String inputUsuario = escaner.nextLine();

            System.out.println("Escriba su contraseña:");
            String inputContrasena = escaner.nextLine();

            if (!inputUsuario.equals(usuario) || !inputContrasena.equals(paso)) {
                System.out.println("Usuario o contraseña incorrectos, intente de nuevo\n");
            } else {
                System.out.println("Ingreso correctamente\n");
                break;
            }
        }

        int menuu;
        do {
            System.out.println("""
                Seleccione la operación:
                1. Par o impar
                2. Promedio de notas
                3. Calcular el IMC
                4. Palabra palindromo
                5. Identidicar cuadrilatero               
                6. Identidica tipo de triangulo 
                7. Calcular Edad  
                8. Horoscopo  
                9. Velocidad, tiempo, distancia  
                10. Numero primo  
                11. Clasificacion por edad  
                12. Tablas de multiplicar  
                13. Area del circulo  
                14. Area del cuadrilatero
                15. Volumen de una esfera  
                16. Volumen de una piramide 
                17. Bumero Capicua  
                18. Hipotenusa                
                19. Salir               
                """);
            menuu = escaner.nextInt();

            switch (menuu) {
                case 1 -> {
                    System.out.println("Ingrese un número:");
                    int caso1 = escaner.nextInt();
                    if (caso1 % 2 == 0) {
                        System.out.println("Es PAR\n");
                    } else {
                        System.out.println("Es IMPAR\n");
                    }
                }
                case 2 -> {
                    double porcentaje1 = 0.30;
                    double porcentaje2 = 0.20;
                    double porcentaje3 = 0.05;
                    double porcentaje4 = 0.05;
                    double porcentaje5 = 0.40;

                    // Nota 1 - TC
                    double nota1;
                    while (true) {
                        System.out.println("Coloque el TC (nota 1):");
                        nota1 = escaner.nextDouble();
                        if (nota1 >= 0 && nota1 <= 5) {
                            break;
                        } else {
                            System.out.println("La nota debe estar entre 0 y 5\n");
                        }
                    }

                    // Nota 2 - Pics
                    double nota2;
                    while (true) {
                        System.out.println("Coloque el Pics (nota 2):");
                        nota2 = escaner.nextDouble();
                        if (nota2 >= 0 && nota2 <= 5) {
                            break;
                        } else {
                            System.out.println("La nota debe estar entre 0 y 5\n");
                        }
                    }

                    // Nota 3 - Auto evaluación
                    double nota3;
                    while (true) {
                        System.out.println("Coloque la auto evaluación (nota 3):");
                        nota3 = escaner.nextDouble();
                        if (nota3 >= 0 && nota3 <= 5) {
                            break;
                        } else {
                            System.out.println("La nota debe estar entre 0 y 5\n");
                        }
                    }

                    // Nota 4 - Coevaluación
                    double nota4;
                    while (true) {
                        System.out.println("Coloque la coevaluación (nota 4):");
                        nota4 = escaner.nextDouble();
                        if (nota4 >= 0 && nota4 <= 5) {
                            break;
                        } else {
                            System.out.println("La nota debe estar entre 0 y 5\n");
                        }
                    }

                    // Nota 5 - Parcial
                    double nota5;
                    while (true) {
                        System.out.println("Coloque el parcial (nota 5):");
                        nota5 = escaner.nextDouble();
                        if (nota5 >= 0 && nota5 <= 5) {
                            break;
                        } else {
                            System.out.println("La nota debe estar entre 0 y 5\n");
                        }
                    }

                    // Calcular promedio ponderado
                    double totalNota = (nota1 * porcentaje1)
                            + (nota2 * porcentaje2)
                            + (nota3 * porcentaje3)
                            + (nota4 * porcentaje4)
                            + (nota5 * porcentaje5);

                    System.out.println("\nSu nota final es: " + totalNota);

                    if (totalNota >= 3.0) {
                        System.out.println("Aprobó la materia");
                    } else {
                        System.out.println("No aprobó, tiene que repetir el semestre :(");
                    }
                }
                case 3 -> {
                    double peso, altura, imc;

                    // Pedir peso
                    while (true) {
                        System.out.println("Ingrese su peso (kg):");
                        peso = escaner.nextDouble();
                        if (peso > 0) {
                            break;
                        } else {
                            System.out.println("El peso debe ser mayor a 0\n");
                        }
                    }

                    // Pedir altura
                    while (true) {
                        System.out.println("Ingrese su altura (metros):");
                        altura = escaner.nextDouble();
                        if (altura > 0) {
                            break;
                        } else {
                            System.out.println("La altura debe ser mayor a 0\n");
                        }
                    }

                    // Calcular IMC
                    imc = peso / (altura * altura);

                    System.out.println("\nSu IMC es: " + imc);

                    // Clasificación
                    if (imc < 18.5) {
                        System.out.println("Esta bajo peso");
                    } else if (imc >= 18.5 && imc <= 24.9) {
                        System.out.println("Esta en peso normal");
                    } else if (imc >= 25 && imc <= 29.9) {
                        System.out.println("Alerta: sobrepeso");
                    } else {
                        System.out.println("Obesidad");
                    }
                }

                case 4 -> {
                    Scanner palindromo = new Scanner(System.in);

                    System.out.println("Ingresar la parabra a indentificar: ");
                    String palabra = palindromo.nextLine();
                    if (!esPalindromo(palabra)) {
                        System.out.println("No es un palindromo");
                    } else {
                        System.out.println(palabra + " Es un palindromo ");

                    }

                }
                case 5 -> {

                    System.out.println("Ingrese el lado 1");
                    double lado1 = escaner.nextDouble();

                    System.out.println("Ingrese el lado 2");
                    double lado2 = escaner.nextDouble();

                    System.out.println("Ingrese el lado 3");
                    double lado3 = escaner.nextDouble();

                    System.out.println("Ingrese el lado 4");
                    double lado4 = escaner.nextDouble();

                    String resultado;

                    if (lado1 == lado2 && lado2 == lado3 && lado3 == lado4) {
                        resultado = "Cuadrado o Rombo";
                    } else if ((lado1 == lado2 && lado3 == lado4) || (lado1 == lado3 && lado2 == lado4)) {
                        resultado = "Rectángulo o Romboide";
                    } else if (lado1 == lado2 || lado1 == lado3 || lado1 == lado4 || lado2 == lado3 || lado2 == lado4 || lado3 == lado4) {
                        resultado = "Trapecio";
                    } else {
                        resultado = "Trapezoide irregular";
                    }

                    System.out.println("Tipo: " + resultado);
                }
                case 6 -> {

                    System.out.println("Ingrese los 3 lados del triangulo");
                    double lado1 = escaner.nextDouble();
                    double lado2 = escaner.nextDouble();
                    double lado3 = escaner.nextDouble();

                    String ladot;

                    if (lado1 == lado2 && lado2 == lado3) {
                        ladot = "El triangulo es EQUILÁTERO";
                    } else if (lado1 == lado2 || lado1 == lado3 || lado2 == lado3) {
                        ladot = "El triangulo es ISÓSCELES";
                    } else {
                        ladot = "El triangulo es ESCALENO";
                    }
                    System.out.println(ladot);

                }
                case 7 -> {

                    System.out.print("Día: ");
                    int dia = escaner.nextInt();

                    System.out.print("Mes: ");
                    int mes = escaner.nextInt();

                    System.out.print("Año: ");
                    int ano = escaner.nextInt();

                    // Crear fecha de nacimiento
                    java.util.Calendar nac = java.util.Calendar.getInstance();
                    nac.set(ano, mes - 1, dia); // Mes - 1 porque Calendar usa 0-11

                    // Obtener fecha actual
                    java.util.Calendar actual = java.util.Calendar.getInstance();

                    // Calcular diferencia
                    int años = actual.get(java.util.Calendar.YEAR) - nac.get(java.util.Calendar.YEAR);
                    int meses = actual.get(java.util.Calendar.MONTH) - nac.get(java.util.Calendar.MONTH);
                    int dias = actual.get(java.util.Calendar.DAY_OF_MONTH) - nac.get(java.util.Calendar.DAY_OF_MONTH);

                    // Ajustar si los días son negativos
                    if (dias < 0) {
                        meses--;
                        // Obtener días del mes anterior
                        java.util.Calendar mesAnterior = (java.util.Calendar) actual.clone();
                        mesAnterior.add(java.util.Calendar.MONTH, -1);
                        int diasMesAnterior = mesAnterior.getActualMaximum(java.util.Calendar.DAY_OF_MONTH);
                        dias += diasMesAnterior;
                    }

                    // Ajustar si los meses son negativos
                    if (meses < 0) {
                        años--;
                        meses += 12;
                    }

                    // Validar
                    if (años < 0 || años > 150) {
                        System.out.println("\nError: Fecha de nacimiento inválida");
                    } else {
                        System.out.println("\n Tu edad es:");
                        System.out.println(años + " años, " + meses + " meses y " + dias + " días");

                        if (años < 18) {
                            System.out.println("Eres menor de edad");
                        } else if (años < 65) {
                            System.out.println("Eres adulto");
                        } else {
                            System.out.println("Eres adulto mayor");
                        }
                    }

                }
                case 8 -> {
                    System.out.print("Ingrese el día de nacimiento: ");
                    int diah = escaner.nextInt();

                    System.out.print("Ingrese el mes de nacimiento en numero: ");
                    int mesh = escaner.nextInt();

                    String signo;

                    if ((mesh == 3 && diah >= 21) || (mesh == 4 && diah <= 19)) {
                        signo = "Aries";
                    } else if ((mesh == 4 && diah >= 20) || (mesh == 5 && diah <= 20)) {
                        signo = "Tauro";
                    } else if ((mesh == 5 && diah >= 21) || (mesh == 6 && diah <= 20)) {
                        signo = "Geminis";
                    } else if ((mesh == 6 && diah >= 21) || (mesh == 7 && diah <= 22)) {
                        signo = "Cancer";
                    } else if ((mesh == 7 && diah >= 23) || (mesh == 8 && diah <= 22)) {
                        signo = "Leo";
                    } else if ((mesh == 8 && diah >= 23) || (mesh == 9 && diah <= 22)) {
                        signo = "Virgo";
                    } else if ((mesh == 9 && diah >= 23) || (mesh == 10 && diah <= 22)) {
                        signo = "Libra";
                    } else if ((mesh == 10 && diah >= 23) || (mesh == 11 && diah <= 21)) {
                        signo = "Escorpion";
                    } else if ((mesh == 11 && diah >= 22) || (mesh == 12 && diah <= 21)) {
                        signo = "Sagitario";
                    } else if ((mesh == 12 && diah >= 22) || (mesh == 1 && diah <= 19)) {
                        signo = "Capricornio";
                    } else if ((mesh == 1 && diah >= 20) || (mesh == 2 && diah <= 18)) {
                        signo = "Acuario";
                    } else if ((mesh == 2 && diah >= 19) || (mesh == 3 && diah <= 20)) {
                        signo = "Piscis";
                    } else {
                        signo = "Fecha inválida";
                    }

                    System.out.println("Su signo zodiacal es: " + signo);
                    break;
                }
                case 9 -> {

                    int opcionesCalcular;

                    do {
                        System.out.println("1. Calcular velocidad");
                        System.out.println("2. Calcular tiempo");
                        System.out.println("3. Calcular distancia");
                        System.out.println("4. Salir");

                        opcionesCalcular = escaner.nextInt();
                        switch (opcionesCalcular) {

                            case 1 -> {
                                System.out.println("Ingrese distancia:");
                                double distanciaC = escaner.nextDouble();

                                System.out.println("Ingrese tiempo:");
                                double tiempoC = escaner.nextDouble();

                                if (tiempoC <= 0) {
                                } else {
                                    double velocidadC = distanciaC / tiempoC;
                                    System.out.println("La velocidad es: " + velocidadC);
                                }
                            }

                            case 2 -> {
                                System.out.println("Ingrese la distancia:");
                                double distanciaC = escaner.nextDouble();

                                System.out.println("Ingrese la velocidad:");
                                double velocidadC = escaner.nextDouble();

                                if (velocidadC <= 0) {
                                    System.out.println("La velocidad debe ser mayor a 0");
                                } else {
                                    double tiempoC = distanciaC / velocidadC;
                                    System.out.println("El tiempo es: " + tiempoC);
                                }
                            }

                            case 3 -> {
                                System.out.println("Ingrese la velocidad:");
                                double velocidadC = escaner.nextDouble();

                                System.out.println("Ingrese el tiempo:");
                                double tiempoC = escaner.nextDouble();

                                double distanciaC = velocidadC * tiempoC;
                                System.out.println("La distancia es: " + distanciaC);
                            }

                            case 4 -> {
                                System.out.println("Fin del menú de cálculos");
                            }

                            default ->
                                System.out.println("Opción inválida");
                        }

                    } while (opcionesCalcular != 4);
                }

                case 10 -> {

                    System.out.println("Ingrese su número");
                    int numeroP = escaner.nextInt();

                    boolean esPrimo = true;

                    if (numeroP < 2) {
                        esPrimo = false;
                    } else if (numeroP == 2) {
                        esPrimo = true;
                    } else if (numeroP % 2 == 0) {
                        esPrimo = false;
                    } else {
                        for (int i = 3; i <= Math.sqrt(numeroP); i += 2) {
                            if (numeroP % i == 0) {
                                esPrimo = false;
                                break;
                            }
                        }
                    }

                    if (esPrimo) {
                        System.out.println("El número " + numeroP + " ES primo");
                    } else {
                        System.out.println("El número " + numeroP + " NO es primo");
                    }
                }

                case 11 -> {
                    System.out.print("Ingresa tu edad: ");
                    int calcularedad = escaner.nextInt();

                    if (calcularedad < 0) {
                        System.out.println("Edad inválida");
                    } else if (calcularedad <= 2) {
                        System.out.println("Clasificación: Bebé");
                    } else if (calcularedad <= 12) {
                        System.out.println("Clasificación: Niño");
                    } else if (calcularedad <= 17) {
                        System.out.println("Clasificación: Adolescente");
                    } else if (calcularedad <= 64) {
                        System.out.println("Clasificación: Adulto");
                    } else {
                        System.out.println("Clasificación: Adulto mayor");
                    }
                }

                case 12 -> {

                    System.out.print("Ingrese el número para la tabla: ");
                    int tabla = escaner.nextInt();

                    boolean validar = true;

                    if (tabla < 0) {
                        validar = false;
                        System.out.println("El número no puede ser negativo");
                    }

                    if (validar) {
                        System.out.println("\nTabla del " + tabla);
                        for (int i = 0; i <= 10; i++) {
                            System.out.println(tabla + " x " + i + " = " + (tabla * i));
                        }
                    }

                }

                case 13 -> {
                    System.out.println("Ingrese el radio del circulo");
                    double radioPana = escaner.nextDouble();
                    if (radioPana <= 0) {
                        System.out.println("el sadio debe ser mayor a cero");
                    } else {
                        double areaCirculo = Math.PI * radioPana * radioPana;
                        System.out.println("el area del circulo es: " + areaCirculo);
                    }
                }

                case 14 -> {

                    int menuCuadrilatero;

                    do {
                        System.out.println("1.cuadrado");
                        System.out.println("2.Rectangulo");
                        System.out.println("3.Trapecio");
                        System.out.println("4.Rombo");
                        System.out.println("5.Salir");

                        menuCuadrilatero = escaner.nextInt();

                        switch (menuCuadrilatero) {

                            case 1 -> {

                                System.out.println("Lado :");
                                double ladoCua = escaner.nextDouble();

                                System.out.println("El area es: " + (ladoCua * ladoCua));
                            }

                            case 2 -> {
                                System.out.println("Base: ");
                                double baseCua = escaner.nextDouble();
                                System.out.println(" Altura: ");
                                double alturaCua = escaner.nextDouble();
                                System.out.println("Área: " + (baseCua * alturaCua));

                            }

                            case 3 -> {

                                System.out.println("Base mayor ");
                                double BaseMayor = escaner.nextDouble();

                                System.out.println("Base meno");
                                double BaseMenor = escaner.nextDouble();

                                System.out.println("Altrua ");
                                double alturaC = escaner.nextDouble();

                                System.out.println("Area " + ((BaseMayor + BaseMenor) / 2 * alturaC));

                            }

                            case 4 -> {
                                System.out.println("Diagonal mayor: ");
                                double DiagoMayor = escaner.nextDouble();

                                System.out.println("Diagonal menor: ");
                                double DiagoMenor = escaner.nextDouble();

                                System.out.println("area: " + (DiagoMayor * DiagoMenor) / 2);
                            }

                            case 5 -> {
                                System.out.println("gracias");
                            }
                            default ->
                                System.out.println("no validdo");

                        }

                    } while (menuCuadrilatero != 5);

                }

                case 15 -> {
                    System.out.println("Ingrese el radio");

                    double EsferaRadio = escaner.nextDouble();

                    double EsferaVolumen = (4.0 / 3.0) * Math.PI * Math.pow(EsferaRadio, 3);

                    System.out.println("El volumen de la esfera es " + EsferaVolumen);

                }

                case 16 -> {
                    System.out.println("Lado de la base: ");
                    double PiramideLado = escaner.nextDouble();

                    System.out.println("Altura ");
                    double PiramideAltura = escaner.nextDouble();

                    double PiramideVolumen = (1.0 / 3.0) * (PiramideLado * PiramideLado) * PiramideAltura;

                    System.out.println("El volumen de la piramide es " + PiramideVolumen);
                }

                case 17 -> {

                    System.out.println("Ingrese el número a saber:");
                    long Ncapicua = escaner.nextLong();

                    if (esCapicua(Ncapicua)) {
                        System.out.println(Ncapicua + " es capicua");
                    } else {
                        System.out.println(Ncapicua + " no es capicua");
                    }
                }

                case 18 -> {
                    
                    System.out.println(" Cateto 1");
                    double Cateto1 = escaner.nextDouble();
                    
                    System.out.println("Cateto 2");
                    double Cateto2 = escaner.nextDouble();
                    
                    double Hipotenusa = Math.sqrt(Cateto1 + Cateto1 * Cateto2 + Cateto2 );
                    
                    System.out.println(" La hipotenusa es: " + Hipotenusa);

                }

                case 19 -> {

                    System.out.println("Saliendo...");
                }
                default ->
                    System.out.println("Opción inválida\n");
            }

        } while (menuu != 19);
    }
}
