package com.hertel.exercise04;

import java.util.Scanner;
import java.util.HashMap;
import java.util.Map;
import java.util.List;
import java.util.LinkedList;

public class Main {

    static Scanner input = new Scanner(System.in);

    static void displayTemperatures(Map<String, Integer> tempMap) {
        for (String key: tempMap.keySet()) {
            int temp = tempMap.get(key);
            System.out.println("City: " + key + ", 5 day average temperature: " + temp);
        }
    }

    static Map<String, Integer> assignTemperatures(List<String> cities, List<Integer> avgTemps) {
        Map<String, Integer> temperatures = new HashMap<>();
        for (int i = 0; i < cities.size(); i++) {
            temperatures.put(cities.get(i), avgTemps.get(i));
        }
        return temperatures;
    }

    static int calc5DayAvg(String[] temps) {
        int fiveDayAvg = 0;
        for (String day:temps) {
            fiveDayAvg += Integer.parseInt(day);
        }
        fiveDayAvg /= temps.length;

        return fiveDayAvg;
    }

    static List<Integer> inputAvgs(List<String> cities) {
        List<Integer> avgs = new LinkedList<>();

        for (String city:cities) {
            System.out.print("What were the avg. temperatures in " + city + " for the last 5 days (separate with spaces): ");
            String tempsFor5Days = input.nextLine();
            String[] temps = tempsFor5Days.split(" ", 5);
            int average = calc5DayAvg(temps);
            avgs.add(average);
        }
        return avgs;
    }

    static List<String> inputCities() {
        List<String> cities = new LinkedList<>();

        System.out.print("Enter the name of a city (or END to stop): ");
        String city = input.nextLine();

        while (!city.toUpperCase().equals("END")) {
            cities.add(city);

            System.out.print("Enter the name of a city (or END to stop): ");
            city = input.nextLine();
        }
        return cities;
    }

    public static void main(String[] args) {
        List<String> cityNames = inputCities();
        List<Integer> avgTemps = inputAvgs(cityNames);

        Map<String, Integer> temperatures = assignTemperatures(cityNames, avgTemps);

        displayTemperatures(temperatures);
    }
}
