# Lab-8_202001178

## Name: Rudra Gohel
## ID: 202001178

**Aim**: The goal of this lab is to learn how to use JUnit to write unit tests for Java programs.

**Tool Used**: Eclipse and JUnit 4

*Lab Exercises*:

&#8594; Created a new Eclipse project named Lab8_202001178, and within the project create a package named myPackage.

![tempsnip](https://user-images.githubusercontent.com/107960916/233317871-af8989d4-c02c-4bd1-b7b7-24ebab2326d9.png)

&#8594; Created a class for a Boa.

![image](https://user-images.githubusercontent.com/107960916/233318490-8761fe78-6f63-47dc-897d-e49d5abf2147.png)

&#8594; Created Junit Test case named testingBoa. Added private Boa jen; and private Boa ken; above @Before.

![image](https://user-images.githubusercontent.com/107960916/233320002-00fb05d8-486f-4288-a2f5-9fbb808fc2a2.png)

&#8594; Testing isHealthy method with the help of testIsHealthy() method. Testing fitsInCage method with the help of testFitsInCage()() method.

All test cases passed: 

![image](https://user-images.githubusercontent.com/107960916/233321896-f2cc38be-e712-4894-b0b2-4c1aab38d9f3.png)

Detects error in case of wrong test case:

![image](https://user-images.githubusercontent.com/107960916/233322404-32b830ee-03ba-4a84-a749-631c5bcc7a3b.png)

![image](https://user-images.githubusercontent.com/107960916/233323063-bc948acd-c16f-4d6d-82b4-3e47123c050d.png)

&#8594; Add a new method lengthInInches() to the Boa class:

![image](https://user-images.githubusercontent.com/107960916/233324175-3720f825-82dd-4afe-86ad-ef16f69ff0d3.png)

&#8594; Testing lengthInInches() method using testlengthInInches() method.

All test cases passed: 

![image](https://user-images.githubusercontent.com/107960916/233325438-1ce86637-4220-48cd-aeec-063eca0865fb.png)

Detects error in case of wrong test case:

![image](https://user-images.githubusercontent.com/107960916/233325677-8e6b5348-3855-4aea-9594-7ae586477bf9.png)

&#8594; Codes:

Boa.java

package myPackage;

public class Boa {
    private String name;
    private int length; // the length of the boa, in feet
    private String favoriteFood;

    public Boa(String name, int length, String favoriteFood) {
        this.name = name;
        this.length = length;
        this.favoriteFood = favoriteFood;
    }

    // returns true if this boa constructor is healthy
    public boolean isHealthy() {
        return this.favoriteFood.equals("granola bars");
    }

    // returns true if the length of this boa constructor is
    // less than the given cage length
    public boolean fitsInCage(int cageLength) {
        return this.length < cageLength;
    }

    // produces the length of the Boa in inches
    public int lengthInInches() {
        return this.length * 12;
    }
}

 testingBoa.java
 
 package myPackage;

import static org.junit.Assert.*;

import org.junit.Before;
import org.junit.Test;

public class testingBoa {
	
	private Boa jen;
	private Boa ken;
	
	@Before
	public void setUp() throws Exception {
		jen = new Boa("Jennifer", 2, "grapes");
		ken = new Boa ("Kenneth", 3, "granola bars");
	}
	
	@Test
	public void testIsHealthy() {
		assertEquals(false, jen.isHealthy());
		assertEquals(true, ken.isHealthy());
	}
	
	@Test
	public void testFitsInCage() {
		assertEquals(true, jen.fitsInCage(7));
		assertEquals(true, ken.fitsInCage(5));
	}
	
	@Test 
	public void testlengthInInches() {
		assertEquals(14, jen.lengthInInches());
		assertEquals(36, ken.lengthInInches());
	}
}
