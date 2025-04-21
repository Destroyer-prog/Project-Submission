# Project-Submission
# A Java application that calculates the area of a shape by typing the name of the shape.
# When the user enters a name, the name, formula, area, and other values will output according to the name default.
# However, if the user enters a name of a polygon or 3D shape, an invalid input message will be outputted.
# The program uses an abstract class and classes that extends that abstract class with an abstract double called getArea().
# Each class has their own methods and their own getArea() returns according to the shape default.
# An array list is used to enter all the options at once in order for the user to know what shapes is the user allowed to enter to prevent invalid inputs.

public abstract class Shape {
    public abstract double getArea();
}

import java.text.DecimalFormat;
public class Circle extends Shape{
    private final double radius;
    
    public Circle(double radius){
        this.radius = radius;
    }
    
    @Override
    public double getArea(){
        return 2 * Math.PI * radius;
    }
    
    @Override
    public String toString(){
        DecimalFormat round = new DecimalFormat("0.##");
        return "Shape: Circle \nRadius: " + round.format(radius) + "\nArea: " + round.format(getArea());
    }
}

import java.text.DecimalFormat;
public class Rectangle extends Shape{
    private final double length;
    private final double width;
    
    public Rectangle(double length, double width) {
        this.length = length;
        this.width = width;
    }
    
    @Override
    public double getArea() {
        return length * width;
    }
    
    @Override
    public String toString(){
        DecimalFormat round = new DecimalFormat("0.##");
        return "Shape: Rectangle \nLength: " + round.format(length) + "\nWidth: " + round.format(width) +"\nArea: " + round.format(getArea());
    }
}

import java.text.DecimalFormat;
public class Triangle extends Shape{
    private final double base;
    private final double height;
    
    public Triangle(double base, double height) {
        this.base = base;
        this.height = height;
    }
    
    @Override
    public double getArea() {
        return (base*height) / 2;
    }
    
    @Override
    public String toString(){
        DecimalFormat round = new DecimalFormat("0.##");
        return "Shape: Triangle \nBase: " + round.format(base) + "\nHeight: " + round.format(height) +"\nArea: " + round.format(getArea());
    }
}

import java.text.DecimalFormat;
public class Square extends Shape{
    private final double sideLength;
    
    public Square(double sideLength) {
        this.sideLength = sideLength;
    }
    
    @Override
    public double getArea() {
        return Math.pow(sideLength, 2);
    }
    
    @Override
    public String toString(){
        DecimalFormat round = new DecimalFormat("0.##");
        return "Shape: Square \nSide Length: " + round.format(sideLength) + "\nArea: " + round.format(getArea());
    }
}

import java.text.DecimalFormat;
public class Ellipse extends Shape{
    private final double a;
    private final double b;
    
    public Ellipse(double a, double b) {
        this.a = a;
        this.b = b;
    }
    
    @Override
    public double getArea() {
        return Math.PI * a * b;
    }
    
    @Override
    public String toString(){
        DecimalFormat round = new DecimalFormat("0.##");
        return "Shape: Ellipse \nSide a: " + round.format(a) + "\nSide b: " + round.format(b) +"\nArea: " + round.format(getArea());
    }
}

import java.text.DecimalFormat;
public class Semicircle extends Shape{
    private final double radius;
    
    public Semicircle(double radius){
        this.radius = radius;
    }
    
    @Override
    public double getArea(){
        return (2 *Math.PI * radius) / 2;
    }
    
    @Override
    public String toString(){
        DecimalFormat round = new DecimalFormat("0.##");
        return "Shape: Semicircle \nRadius: " + round.format(radius) + "\nArea: " + round.format(getArea());
    }
}

import java.text.DecimalFormat;
public class Rhombus extends Shape{
    private final double diagonal1;
    private final double diagonal2;
    
    public Rhombus(double diagonal1, double diagonal2){
        this.diagonal1 = diagonal1;
        this.diagonal2 = diagonal2;
    }
    
    @Override
    public double getArea(){
        return (diagonal1 * diagonal2) / 2;
    }
    
    @Override
    public String toString(){
        DecimalFormat round = new DecimalFormat("0.##");
        return "Shape: Rhombus \nLength: " + round.format(diagonal1) + "\nHeight: " + round.format(diagonal2) + "\nArea: " + round.format(getArea());
    }
}

import java.text.DecimalFormat;
public class Trapezoid extends Shape{
    private final double a;
    private final double b;
    private final double h;
    
    public Trapezoid(double a, double b, double h){
        this.a = a;
        this.b = b;
        this.h = h;
    }
    
    @Override
    public double getArea(){
        return ((a + b) * h) / 2;
    }
    
    @Override
    public String toString(){
        DecimalFormat round = new DecimalFormat("0.##");
        return "Shape: Trapezoid \nBase a: " + round.format(a) + "\nBase b: " + round.format(b) + "\nHeight: " + "\nArea: " + round.format(getArea());
    }
}

import java.text.DecimalFormat;
public class Parallelogram extends Shape{
    private final double base;
    private final double height;
    
    public Parallelogram(double base, double height){
        this.base = base;
        this.height= height;
    }
    
    @Override
    public double getArea(){
        return base * height;
    }
    
    @Override
    public String toString(){
        DecimalFormat round = new DecimalFormat("0.##");
        return "Shape: Parallelogram \nBase: " + round.format(base) + "\nHeight: " + round.format(height) + "\nArea: " + round.format(getArea());
    }
}

import java.text.DecimalFormat;
public class Sector extends Shape{
    private final double doubleCentralAngle;
    private final double radius;
    
    public Sector(double doubleCentralAngle, double radius){
        this.doubleCentralAngle = doubleCentralAngle;
        this.radius = radius;
    }
    
    @Override
    public double getArea(){
        return (doubleCentralAngle / 360) * Math.PI * Math.pow(radius, 2);
    }
    
    @Override
    public String toString(){
        DecimalFormat round = new DecimalFormat("0.##");
        return "Shape: Sector \nCentral Angle: " + doubleCentralAngle + "\nRadius: " + round.format(radius) + "\nArea: " + round.format(getArea());
    }
}

import java.util.Scanner;
public class CourseProjectShapeAreaCalculator {

    public static void main(String[] args) {
        String shape;
        Scanner scan = new Scanner(System.in);
        double x = (Math.random() * 100) + 1;
        double y = (Math.random() * 100) + 1;
        double z = (Math.random() * 100) + 1;
        String[] shapeList = {"Circle", "Rectangle", "Triangle", "Square", "Ellipse", "Semicircle", "Rhombus", "Trapezoid", "Parallelogram", "Sector"};
        
        System.out.println("Enter a shape: (Do not enter polygons or 3D shapes)");
        System.out.println("Here are the options:");
        
        for (String shapeList1 : shapeList) {
            System.out.println(shapeList1);
        }
        
        System.out.println(" ");
        shape = scan.nextLine();
        System.out.println(" ");
        if (shape.equalsIgnoreCase("Circle")){
           Shape circle = new Circle(x);
           System.out.println("Formula: A = (3.14 * r^2) / 2");
           System.out.println(circle.toString());
        } else if (shape.equalsIgnoreCase("Rectangle")){
            Shape rectangle = new Rectangle(x, y);
            System.out.println("Formula: A = l * h");
            System.out.println(rectangle.toString());
        } else if (shape.equalsIgnoreCase("Triangle")){
            Shape triangle = new Triangle(x, y);
            System.out.println("formula: A = (b * h) / 2");
            System.out.println(triangle.toString());
        } else if (shape.equalsIgnoreCase("Square")){
            Shape square = new Square(x);
            System.out.println("Formula: A = s^2");
            System.out.println(square.toString());
        } else if (shape.equalsIgnoreCase("Ellipse")){
            Shape ellipse = new Ellipse(x, y);
            System.out.println("Formula: A = 3.14 * a * b");
            System.out.println(ellipse.toString());
        } else if(shape.equalsIgnoreCase("Semicircle")){
            Shape semicircle = new Semicircle(x);
            System.out.println("Formula: A = (2 * 3.14 * r) / 2");
            System.out.println(semicircle.toString());
        } else if(shape.equalsIgnoreCase("Rhombus")){
            Shape rhombus = new Rhombus(x, y);
            System.out.println("Formula: A = (d1 * d2) / 2");
            System.out.println(rhombus.toString());
        } else if(shape.equalsIgnoreCase("Trapezoid")){
            Shape trapezoid = new Trapezoid(x, y, z);
            System.out.println("Formula: A = ((a + b) / 2) * h");
            System.out.println(trapezoid.toString());
        } else if(shape.equalsIgnoreCase("Parallelogram")){
            Shape parallelogram = new Parallelogram(x, y);
            System.out.println("Formula: A = b * h");
            System.out.println(parallelogram.toString());
        } else if(shape.equalsIgnoreCase("Sector")){
            double theta = (int) ((Math.random() * 180) + 1);
            double r = ((Math.random() * 100) + 1);
            System.out.println("Formula: A = (n/360) * 3.14 * r^2");
            Shape sector = new Sector(theta, r);
            System.out.println(sector.toString());
        } else {
            System.out.println("Invalid input! Enter a shape from the list. Make sure is not a polygon or a 3D shape.");
        }
    }
}
