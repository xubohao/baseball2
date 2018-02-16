# baseball2
package data;

import java.util.Scanner;

public class PlayerInfo {
	
	/**
	 * Default constructor: 
	 *  create an empty player info container.
	 */
	PlayerInfo() {
		// do nothing here.
	}
	
	// calculating methods:
	
	/**
	 * The batting average (BA) is defined by 
	 * 	the number of hits divided by at bats or the number of balls faced.
	 * @return the BS value
	 */
	public double calculateBA()	{
		return (double)H / AB;
	}
	
	/**	
	 * On base percentage (OBP) is a measure of how often a batter reaches base.
	 * 	OBP = (H + BB + HBP) / (AB + BB + HBP + SF)
	 * For the limitation of inputs, here I use (H + BB) / (AB + BB).
	 * @return the OBP value
	 */
	public double calculateOBP() {
		return (double)(H + BB) / (AB + BB);
	}
	
	/**
	 * Slugging percentage is a popular measure of the power of a hitter.
	 * 	SLG = (1B + 2 ¡Á 2B + 3 ¡Á 3B + 4 ¡Á HR) / AB
	 * @return the SLG value
	 */
	public double calculateSLG() {
		return (double)(H + 2 * _2B + 3 * _3B + 4 * HR) / AB;
	}
	
	/**
	 * (for the term, I think "OPS" should be the standard name.)
	 * the sum of a player's on-base percentage and slugging average.
	 * @return the OPS value
	 */
	public double calculateOPS() {
		return calculateOBP() + calculateSLG();
	}
	
	/**
	 * TB is a baseball statistic that 
	 * 	adds together the total base hits that a batter produces.
	 * @return the TB value
	 */
	public int calculateTB() {
		return H + 2 * _2B + 3 * _3B + 4 * HR; 
	}

	// getters and setters:
	
    /**
     * @return the aB
     */
    public int getAB() {
        return AB;
    }

    /**
     * @param aB the aB to set
     */
    public void setAB(int aB) {
        AB = aB;
    }

    /**
     * @return the h
     */
    public int getH() {
        return H;
    }

    /**
     * @param h the h to set
     */
    public void setH(int h) {
        H = h;
    }

    /**
     * @return the _2B
     */
    public int get_2B() {
        return _2B;
    }

    /**
     * @param _2b the _2B to set
     */
    public void set_2B(int _2b) {
        _2B = _2b;
    }

    /**
     * @return the _3B
     */
    public int get_3B() {
        return _3B;
    }

    /**
     * @param _3b the _3B to set
     */
    public void set_3B(int _3b) {
        _3B = _3b;
    }

    /**
     * @return the hR
     */
    public int getHR() {
        return HR;
    }

    /**
     * @param hR the hR to set
     */
    public void setHR(int hR) {
        HR = hR;
    }

    /**
     * @return the r
     */
    public int getR() {
        return R;
    }

    /**
     * @param r the r to set
     */
    public void setR(int r) {
        R = r;
    }

    /**
     * @return the bB
     */
    public int getBB() {
        return BB;
    }

    /**
     * @param bB the bB to set
     */
    public void setBB(int bB) {
        BB = bB;
    }

    /**
     * @return the name
     */
    public String getName() {
        return name;
    }

    /**
     * @param name the name to set
     */
    public void setName(String name) {
        this.name = name;
    }

    // private data section: 
    private String name;
    private int AB;
    private int H;
    private int _2B;
    private int _3B;
    private int HR;
    private int R;
    private int BB;
    
    // main method: test use
    public static void main(String[] args) {
    	PlayerInfo info = new PlayerInfo();
    	
    	Scanner scanner = new Scanner(System.in);
    	System.out.println("Please input player information:");
    	System.out.print("name:\t");
		info.setName(scanner.next());
    	System.out.print("AB:\t");
		info.setAB(scanner.nextInt());
    	System.out.print("H:\t");
		info.setH(scanner.nextInt());
    	System.out.print("_2B:\t");
		info.set_2B(scanner.nextInt());
    	System.out.print("_3B:\t");
		info.set_3B(scanner.nextInt());
    	System.out.print("HR:\t");
		info.setHR(scanner.nextInt());
    	System.out.print("R:\t");
		info.setR(scanner.nextInt());
    	System.out.print("BB:\t");
		info.setBB(scanner.nextInt());	
		scanner.close();
    	System.out.println("Thank you!");
    	
    	System.out.println("Here is the required statistics:");
        System.out.format("BA:\t%3.3f\n", info.calculateBA());
        System.out.format("OBP:\t%3.3f\n", info.calculateOBP());
        System.out.format("SLG:\t%3.3f\n", info.calculateSLG());
        System.out.format("OPS:\t%3.3f\n", info.calculateOPS());
        System.out.format("TB:\t%d\n", info.calculateTB());
    	
        System.out.println("End.");
    }
}

