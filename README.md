# EncapsulationChallengeTwo
package academy.learnprogrmming;

public class Main {

    static class Printer {
        private int tonerLevel;
        private int pagesPrinted;
        private boolean isDuplex;


        public Printer(int tonerLevel, boolean isDuplex) {
            if (tonerLevel > -1 && tonerLevel <= 100) {
                this.tonerLevel = tonerLevel;
            } else {
                this.tonerLevel = -1;
            }
            this.isDuplex = isDuplex;


        }

        public int addToner(int tonerAmount) {
            if (tonerAmount > 0 && tonerAmount <= 100) {
                if (tonerLevel + tonerAmount > 100) {
                    return -1;
                } else {
                    tonerLevel += tonerAmount;
                }
                return tonerLevel;
            }
            return -1;
        }

        public int printPages(int pages) {
            int pagesToPrint = pages;
            if (isDuplex == true) {
                pagesToPrint = (pages / 2) + (pages % 2);
                System.out.println("Printing in dublex mode");
            }
            this.pagesPrinted += pagesToPrint;
            return pagesToPrint;
        }

        public int getPagesPrinted() {

            return pagesPrinted;
        }

    }


    public static void main(String[] args) {

        Printer printer = new Printer(50, true);
        System.out.println(printer.addToner(50));
        System.out.println("initial page count = " + printer.getPagesPrinted());
        int pagesPrinted = printer.printPages(4);
        System.out.println("Pages printed was " + pagesPrinted + " new total print count for printer = " + printer.getPagesPrinted());
        pagesPrinted = printer.printPages(2);
        System.out.println("Pages printed was " + pagesPrinted + " new total print count for printer = " + printer.getPagesPrinted());


    }
}

"C:\Program Files\Java\jdk-15.0.1\bin\java.exe" "-javaagent:C:\Users\nadiy\OneDrive\Desktop\IntelliJ IDEA Community Edition 2020.2.3\lib\idea_rt.jar=59146:C:\Users\nadiy\OneDrive\Desktop\IntelliJ IDEA Community Edition 2020.2.3\bin" -Dfile.encoding=UTF-8 -classpath C:\Users\nadiy\IdeaProjects\EncapsulationChallenge\out\production\EncapsulationChallenge academy.learnprogrmming.Main
100
initial page count = 0
Printing in dublex mode
Pages printed was 2 new total print count for printer = 2
Printing in dublex mode
Pages printed was 1 new total print count for printer = 3

Process finished with exit code 0
