/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 */

package com.mycompany.prestamo;

/**
 *
 * @author Martin Montes
 */
import java.util.Scanner;

class Anualidad {
    private double renta;
    private double tasaInteres;
    private int numeroPagos;
    private boolean esAnticipada;

    public Anualidad(double renta, double tasaInteres, int numeroPagos, boolean esAnticipada) {
        this.renta = renta;
        this.tasaInteres = tasaInteres;
        this.numeroPagos = numeroPagos;
        this.esAnticipada = esAnticipada;
    }

    public double calcularValorPresente() {
        double valorPresente;
        if (esAnticipada) {
            valorPresente = renta * ((1 - Math.pow(1 + tasaInteres, -numeroPagos)) / tasaInteres) * (1 + tasaInteres);
        } else {
            valorPresente = renta * ((1 - Math.pow(1 + tasaInteres, -numeroPagos)) / tasaInteres);
        }
        return valorPresente;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Solicitar datos
        System.out.print("Ingrese la renta (pago por periodo): ");
        double renta = scanner.nextDouble();

        System.out.print("Ingrese la tasa de interes (en decimal): ");
        double tasaInteres = scanner.nextDouble();

        System.out.print("Ingrese el numero de pagos: ");
        int numeroPagos = scanner.nextInt();

        System.out.print("Es una anualidad anticipada? (true/false): ");
        boolean esAnticipada = scanner.nextBoolean();

        // Crear objeto Anualidad
        Anualidad anualidad = new Anualidad(renta, tasaInteres, numeroPagos, esAnticipada);

        // Calcular y mostrar el valor presente
        double valorPresente = anualidad.calcularValorPresente();
        System.out.printf("El valor presente de la anualidad es: %.2f\n", valorPresente);

        scanner.close();
    }
}