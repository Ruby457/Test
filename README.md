# Test
Paypal.com

package testingstar;

import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;

public class PayPal {

	public static void main(String[] args) {
		// TODO Auto-generated method stub

		WebDriver driver = new ChromeDriver();
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\ruby\\eclipse-workspace\\Selenium\\chromedriver.exe");
		driver.manage().window().maximize();

		driver.manage().timeouts().implicitlyWait(60, TimeUnit.SECONDS);
		// 1. user should Open google.com
		driver.get("https://www.google.com");
		
		
	 //2.user Check that the google logo is visible
			driver.findElement(By.xpath("//img[@id='hplogo']")).isSelected();
		
		
		//3. user Check there are two options present: "Google Search" and "I'm Feeling Lucky"
				
		 driver.findElement(By.name("btnK")).isDisplayed();
		 driver.findElement(By.id(("gbqfbb"))).isDisplayed();
		 
		 
		 //4. Enter text "PayPal" and click "I'm Feeling Lucky"
		 WebElement textbox = driver.findElement(By.name("q"));
		    textbox.sendKeys("paypal");
		    WebElement button = driver.findElement(By.name("btnk"));
		    button.click();
		    
		    
		    //5 .Check the url is now "https://www.paypal.com/"
		driver.get("https://www.paypal.com/");
		
		//6 Click "Sitemap"
		
		driver.findElement(By.tagName("Sitemap")).click();
		//7. Check the url is now "https://www.paypal.com/us/webapps/mpp/full-sitemap"
		driver.getCurrentUrl();
		
		//8Store all of the links on this page into a list and then print them all to system.out
		java.util.List<WebElement> links = driver.findElements(By.tagName("a"));
		 
		 System.out.println(links.size());
		 
		 for (int i = 1; i<=links.size(); i=i+1)
		 
		 {
		 
		 System.out.println(links.get(i).getText());
	}
	

}
