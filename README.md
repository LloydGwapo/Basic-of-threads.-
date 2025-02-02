package basicsyntax;

public class Basicsofthreads {

	// Demonstrating the basics of threads in Java
	public class ThreadBasics {

	    // Thread by extending the Thread class
	    static class MyThread extends Thread {
	        @Override
	        public void run() {
	            for (int i = 0; i < 5; i++) {
	                System.out.println("MyThread is running: " + i);
	                try {
	                    Thread.sleep(500); // Pauses for 500 milliseconds
	                } catch (InterruptedException e) {
	                    System.out.println("MyThread interrupted.");
	                }
	            }
	        }
	    }

	    // Thread by implementing the Runnable interface
	    static class MyRunnable implements Runnable {
	        @Override
	        public void run() {
	            for (int i = 0; i < 5; i++) {
	                System.out.println("MyRunnable is running: " + i);
	                try {
	                    Thread.sleep(500); // Pauses for 500 milliseconds
	                } catch (InterruptedException e) {
	                    System.out.println("MyRunnable interrupted.");
	                }
	            }
	        }
	    }

	    public static void main(String[] args) {
	        System.out.println("Main thread starts.");

	        // Using the Thread class
	        MyThread thread1 = new MyThread();
	        thread1.start();

	        // Using the Runnable interface
	        Thread thread2 = new Thread(new MyRunnable());
	        thread2.start();

	        // Main thread continues
	        for (int i = 0; i < 5; i++) {
	            System.out.println("Main thread: " + i);
	            try {
	                Thread.sleep(500); // Pauses for 500 milliseconds
	            } catch (InterruptedException e) {
	                System.out.println("Main thread interrupted.");
	            }
	        }

	        System.out.println("Main thread ends.");
	}
	}
}
