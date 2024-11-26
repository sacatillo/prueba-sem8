/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 */

package com.mycompany.restaurante_cell;

/**
 *
 * @author Martin Montes
 */
import java.util.ArrayList;
import java.util.Scanner;

class Cliente {
    String nombre;
    String direccion;
    String telefono;
    boolean esFrecuente;
    boolean esTerceraEdad;

    public Cliente(String nombre, String direccion, String telefono, boolean esFrecuente, boolean esTerceraEdad) {
        this.nombre = nombre;
        this.direccion = direccion;
        this.telefono = telefono;
        this.esFrecuente = esFrecuente;
        this.esTerceraEdad = esTerceraEdad;
    }
}

class Pedido {
    String tipoComida;
    double precio;

    public Pedido(String tipoComida, double precio) {
        this.tipoComida = tipoComida;
        this.precio = precio;
    }
}

public class Restaurante {
    static double precioEconomica;
    static double precioRegular;
    static double precioPremium;
    static Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        // Ingreso de precios del día
        System.out.print("Ingrese el precio de la comida economica: ");
        precioEconomica = scanner.nextDouble();
        System.out.print("Ingrese el precio de la comida regular: ");
        precioRegular = scanner.nextDouble();
        System.out.print("Ingrese el precio de la comida premium: ");
        precioPremium = scanner.nextDouble();
        scanner.nextLine(); // Limpiar el buffer

        boolean continuarClientes = true;

        while (continuarClientes) {
            // Ingreso de datos del cliente
            System.out.print("Ingrese el nombre completo del cliente: ");
            String nombre = scanner.nextLine();
            System.out.print("Ingrese la direccion del cliente: ");
            String direccion = scanner.nextLine();
            System.out.print("Ingrese el numero de telefono del cliente: ");
            String telefono = scanner.nextLine();
            System.out.print("Es cliente frecuente? (S/N): ");
            boolean esFrecuente = scanner.nextLine().equalsIgnoreCase("S");
            System.out.print("Es cliente de la tercera edad? (S/N): ");
            boolean esTerceraEdad = scanner.nextLine().equalsIgnoreCase("S");

            Cliente cliente = new Cliente(nombre, direccion, telefono, esFrecuente, esTerceraEdad);

            // Ciclo para tomar pedidos
            ArrayList<Pedido> pedidos = new ArrayList<>();
            double totalVentas = 0;
            boolean continuarPedidos = true;

            while (continuarPedidos) {
                System.out.println("Seleccione el tipo de comida:");
                System.out.println("1. Economica");
                System.out.println("2. Regular");
                System.out.println("3. Premium");
                int opcion = scanner.nextInt();

                String tipoComida = "";
                double precio = 0;

                switch (opcion) {
                    case 1:
                        tipoComida = "Economica";
                        precio = precioEconomica;
                        break;
                    case 2:
                        tipoComida = "Regular";
                        precio = precioRegular;
                        break;
                    case 3:
                        tipoComida = "Premium";
                        precio = precioPremium;
                        break;
                    default:
                        System.out.println("Opcion no valida.");
                        continue;
                }

                Pedido pedido = new Pedido(tipoComida, precio);
                pedidos.add(pedido);
                totalVentas += pedido.precio;

                // Preguntar si se desea agregar otro pedido
                System.out.print("Desea agregar otro pedido? (S/N): ");
                continuarPedidos = scanner.next().equalsIgnoreCase("S");
                scanner.nextLine(); // Limpiar el buffer
            }

            // Calcular descuentos
            double descuento = 0;
            if (cliente.esFrecuente) {
                descuento = 0.15;
            } else if (cliente.esTerceraEdad) {
                descuento = 0.25;
            }

            double totalConDescuento = totalVentas * (1 - descuento);

            // Mostrar resumen de ventas
            System.out.println("\nResumen de Ventas:");
            System.out.println("Nombre del Cliente: " + cliente.nombre);
            System.out.println("Dirección: " + cliente.direccion);
            System.out.println("Telefono: " + cliente.telefono);
            System.out.println("Total Ventas: $" + totalVentas);
            System.out.println("Descuento aplicado: " + (descuento * 100) + "%");
            System.out.println("Total a pagar: $" + totalConDescuento);

            // Preguntar si hay otro cliente
            System.out.print("Desea ingresar otro cliente? (S/N): ");
            continuarClientes = scanner.nextLine().equalsIgnoreCase("S");
 }

        scanner.close();
    }
}