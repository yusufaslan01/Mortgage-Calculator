# Mortgage-Calculator
Calculates Monthly Payment Amount for Mortgage

package com.Aslan;

import java.text.NumberFormat;
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
	// Constants First
        final byte MONTHS = 12;
        final byte PERCENTAGE = 100;

        Scanner scanme = new Scanner(System.in);

        System.out.print("Principal: ");
        float principal = scanme.nextFloat();

        System.out.print("Period (Years): ");
        int year = scanme.nextInt();
        int n = year * MONTHS;

        System.out.print("Annual Interest Rate: ");
        double annualInterest = scanme.nextDouble();
        double r= annualInterest/(MONTHS*PERCENTAGE);

        double mortgagePayment = principal *
                ( r * Math.pow(1+r,n))/
                (Math.pow(1+r,n)-1);
        NumberFormat mymoney = NumberFormat.getCurrencyInstance();
        System.out.print("Mortgage: "+mymoney.format(mortgagePayment));


    }
}
