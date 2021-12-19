# Selenium
Displaying the values of a table in console from a web page 
package htmlpack;

import java.util.List;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class htmlclass {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		System.setProperty("webdriver.chrome.driver","C:\\chromedriver.exe");
		WebDriver wd=new ChromeDriver();
		wd.get("http://demo.guru99.com/test/table.html");
		WebElement mytable=wd.findElement(By.xpath("/html/body/table/tbody"));
		
		List < WebElement > rows_table = mytable.findElements(By.tagName("tr"));
		int rows_count = rows_table.size();
		for(int row = 0; row < rows_count; row++) {
			List < WebElement > Columns_row = rows_table.get(row).findElements(By.tagName("td"));
			int columns_count = Columns_row.size();
			System.out.println("Number of cells In row " + row + " are "+ columns_count);
			for(int column = 0; column < columns_count; column++)
			{
				String celtext = Columns_row.get(column).getText();
				System.out.println("Cell value of row number "+ row + " and column number " + column + " Is " + celtext());
				
			}
		System.out.println("-------------------------------------------------------------------");
		}
		
	}

	private static String celtext() {
		// TODO Auto-generated method stub
		return null;
	}
	
}
