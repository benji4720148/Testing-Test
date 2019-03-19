import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.support.ui.Select;
import org.testng.Assert;
import org.testng.annotations.Test;

import static java.lang.Double.*;
import static java.lang.String.*;
import static java.lang.Thread.sleep;
import static org.junit.Assert.assertThat;
import static org.junit.Assert.assertTrue;
import static org.openqa.selenium.By.name;

// My detailed approaching to solving the following challenges


public class massMutual {
    @Test

    public void createTestObjectives () throws InterruptedException {

        WebDriver driver = new ChromeDriver();  //using the chrome driver because test has to support chrome


        //Verify the right count of values appear

        WebElement label1 = driver.findElement(name("txt_val_1"));
        WebElement label2 = driver.findElement(name("txt_val_2"));
        WebElement label3 = driver.findElement(name("txt_val_4"));
        WebElement label4 = driver.findElement(name("txt_val_5"));
        WebElement label5 = driver.findElement(name("txt_val_6"));
        WebElement total = driver.findElement(name("txt_ttl_val"));


        Assert.assertEquals(true, label1.isDisplayed());
        Assert.assertEquals(true, label2.isDisplayed());
        Assert.assertEquals(true, label3.isDisplayed());
        Assert.assertEquals(true, label4.isDisplayed());
        Assert.assertEquals(true, label5.isDisplayed());


        /* Verify the values on the screen are greater than 0 */  /*I am only verifying value of first label*/
        double actualVal = parseDouble(valueOf(label1)); //to convert string value of label1 into a double val
        double actualVal2 = parseDouble(valueOf(label2));
        double actualVal3 = parseDouble(valueOf(label3));
        double actualVal4 = parseDouble(valueOf(label4));
        double actualVal5 = parseDouble(valueOf(label5));
        double actualTotal = parseDouble(valueOf(total));

            if (actualVal >= 0){
                System.out.print("The value in" + label1 + "is greater than 0");
            }
            else {
                System.out.print("The value in " + label1 + "is not greater than 0");
            }


        // Verify the total balance is correct based on the values listed on the screen
             double totalBalance = actualVal + actualVal2 + actualVal3 + actualVal4 + actualVal5;

            if (totalBalance == actualTotal){
                System.out.println("The values listed on the screen are correct");
            }else
            {
                System.out.print("The values listed on the screen are not correct");
            }


            // verify the values are formatted as currencys
            if (label1.getText().equals("$122,365.24")){

                System.out.println("The value for" + label1 + " is formatted as a currency");
            }else {
                System.out.print("The value is not foramatted as a currency");
            }

            //verify the total balance matches the sum of the values
             if (totalBalance == actualTotal){
                System.out.println("The values listed on the screen are correct");
                 }else
                 {
                 System.out.print("The values listed on the screen are not correct");
                }


    }
}
