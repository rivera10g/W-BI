package com.pruebasbi.examen;
import java.awt.AWTException;
import java.awt.Robot;
import java.awt.Toolkit;
import java.awt.datatransfer.StringSelection;
import java.awt.event.KeyEvent;
import java.sql.Driver;
import java.time.Duration;
import java.util.Set;
import org.junit.Before;
import org.junit.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.openqa.selenium.Keys;


public class PruebasAtom {
	WebDriver driver;


	@Before
	public void setup(){

		System.setProperty("webdriver.chrome.driver","C:\\Users\\Consultor\\Downloads\\chromedriver-win64\\chromedriver.exe");
	        
	        driver = new ChromeDriver();
	        driver.get("https://demoqa.com/ ");
	        driver.manage().window().maximize();
	    }
	@Test
	public void test() throws InterruptedException, AWTException {
	
		/* ELEMENTS 1-3  */
		WebDriverWait wait = new WebDriverWait(driver,Duration.ofSeconds(10));
        WebElement obj1 = wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("/html/body/div[2]/div/div/div[2]/div/div[1]")));
        obj1.click();
      
		
		/* FORMS 4 
		WebDriverWait wait2 = new WebDriverWait(driver,Duration.ofSeconds(10));
        WebElement obj1 = wait2.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("/html/body/div[2]/div/div/div[2]/div/div[2]")));
        obj1.click();
        */
         
		
		/* BOOK STORE 5
		WebDriverWait wait2 = new WebDriverWait(driver,Duration.ofSeconds(10));
        WebElement obj1 = wait2.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("/html/body/div[2]/div/div/div[2]/div/div[6]")));
        obj1.click();
        */
       
        
        /////////////////////////////////////////////////////////////////////////////////////////////////////////////
        /////////////////////////////////////////////////////////////////////////////////////////////////////////////
        /////////////////////////////////////////////////////////////////////////////////////////////////////////////

        
        /* CHECK BOX (1)  */
        WebElement obj2 = driver.findElement(By.xpath("//span[text()='Check Box']"));
        obj2.click();    
        
        WebElement obj3 = wait.until(ExpectedConditions.elementToBeClickable(By.xpath("//button[@class='rct-collapse rct-collapse-btn']")));
        obj3.click();
        
        WebElement obj4 = wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("/html/body/div[2]/div/div/div[2]/div[2]/div[2]/div/ol/li/ol/li[3]/span/button")));
        obj4.click();
        
        
        WebElement obj5 = driver.findElement(By.xpath("//span[text()='Word File.doc']"));
        obj5.click();   
        
        WebElement obj6 = wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//span[text()='Excel File.doc']")));
        obj6.click();
      

        /////////////////////////////////////////////////////////////////////////////////////////////////////////////
        /* DYNAMIC PROPERTIES (2)
       
        WebElement obj4 = driver.findElement(By.xpath("//span[text()='Dynamic Properties']"));
        JavascriptExecutor jsExecutor = (JavascriptExecutor) driver;
        jsExecutor.executeScript("arguments[0].click();", obj4);
        
        WebDriverWait wait2 = new WebDriverWait(driver, Duration.ofSeconds(5));
        WebElement obj5 = wait2.until(ExpectedConditions.visibilityOfElementLocated(By.id("colorChange")));
        obj5.click();
        */
        
   
        /////////////////////////////////////////////////////////////////////////////////////////////////////////////
        
        /* WEB TABLES (3)
        WebElement obj6 = driver.findElement(By.xpath("//span[text()='Web Tables']"));
        obj6.click();
        
        WebElement obj7 = driver.findElement(By.id("addNewRecordButton"));
        obj7.click();
        
        WebElement obj8 = driver.findElement(By.id("firstName"));
        obj8.sendKeys("Juan");
        
        WebElement obj9 = driver.findElement(By.id("lastName"));
        obj9.sendKeys("Perez");
        
        WebElement obj10 = driver.findElement(By.id("userEmail"));
        obj10.sendKeys("test@test.bi.com.gt");
        
        WebElement obj11 = driver.findElement(By.id("age"));
        obj11.sendKeys("22");
        
        WebElement obj12 = driver.findElement(By.id("salary"));
        obj12.sendKeys("8000");
        
        WebElement obj13 = driver.findElement(By.id("department"));
        obj13.sendKeys("Guatemala");
        
        WebElement obj14 = driver.findElement(By.id("submit"));
        obj14.click();
        */
        
        
        /////////////////////////////////////////////////////////////////////////////////////////////////////////////  
        
        /* FORMULARIO FORMS (4) 
        WebElement obj4 = driver.findElement(By.xpath("//span[text()='Practice Form']"));
        JavascriptExecutor jsExecutor = (JavascriptExecutor) driver;
        jsExecutor.executeScript("arguments[0].click();", obj4);
        
        WebElement obj8 = driver.findElement(By.id("firstName"));
        obj8.sendKeys("Carlos");
        
        WebElement obj9 = driver.findElement(By.id("lastName"));
        obj9.sendKeys("Rivera");
        
        WebElement obj10 = driver.findElement(By.id("userEmail"));
        obj10.sendKeys("test@test.bi.com.gt");
        
        
        WebElement obj12 = driver.findElement(By.xpath("//label[@for='gender-radio-1']"));
        obj12.click();
  
        WebElement obj13 = driver.findElement(By.id("userNumber"));
        obj13.sendKeys("1234567890");

        WebElement dateField = driver.findElement(By.id("dateOfBirthInput"));
        dateField.click();
        WebElement yearDropdown = driver.findElement(By.className("react-datepicker__year-select"));
        yearDropdown.click();
        driver.findElement(By.xpath("//option[text()='2001']")).click();
        WebElement monthDropdown = driver.findElement(By.className("react-datepicker__month-select"));
        monthDropdown.click();
        driver.findElement(By.xpath("//option[text()='May']")).click();
        driver.findElement(By.xpath("//div[text()='13']")).click();
        
        WebElement subjectsInput = driver.findElement(By.id("subjectsInput"));
        subjectsInput.click();
        subjectsInput.sendKeys("Math");
        // Esperar a que aparezcan las sugerencias y seleccionar la opción "Math"
        WebDriverWait wait3 = new WebDriverWait(driver,Duration.ofSeconds(10));
        By mathOptionLocator = By.xpath("//div[text()='Maths']");
        wait3.until(ExpectedConditions.elementToBeClickable(mathOptionLocator));
        WebElement mathOption = driver.findElement(mathOptionLocator);
        Actions actions = new Actions(driver);
        actions.doubleClick(mathOption).perform();
        String fieldValue = subjectsInput.getAttribute("value");
        if (fieldValue.equals("Math")) {
            System.out.println("El campo está lleno con 'Math'");
        } else {
            System.out.println("El campo no se llenó correctamente");
        }
        
        WebElement obj14 = driver.findElement(By.xpath("//label[contains(text(),'Sports')]"));
        obj14.click();
        
        WebElement obj15 = driver.findElement(By.id("uploadPicture"));
        obj15.sendKeys("C:\\Users\\Consultor\\Desktop\\archivo.txt");
        
        WebElement obj16 = driver.findElement(By.id("currentAddress"));
        obj16.sendKeys("Banco Industrial Zona 4. 7ª. Avenida 5-10, Zona 4 Centro Financiero Torre I");
        
        WebDriverWait wait4 = new WebDriverWait(driver, Duration.ofSeconds(10));
        try {
            WebElement dropdown1 = wait4.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div/div[2]/div[2]/div[2]/form/div[10]/div[2]/div/div")));
            dropdown1.click();

            WebElement input1 = wait4.until(ExpectedConditions.presenceOfElementLocated(By.xpath("//input[@id='react-select-3-input']")));
            input1.sendKeys("NCR");
            input1.sendKeys(Keys.ENTER);  
        } catch (Exception e) {
            e.printStackTrace();
        }
        
        WebDriverWait wait5 = new WebDriverWait(driver, Duration.ofSeconds(10));
        try {
            WebElement dropdown2 = wait5.until(ExpectedConditions.elementToBeClickable(By.xpath("/html/body/div[2]/div/div/div[2]/div[2]/div[2]/form/div[10]/div[3]/div/div/div[1]")));
            dropdown2.click();

            WebElement input2 = wait5.until(ExpectedConditions.presenceOfElementLocated(By.xpath("//input[@id='react-select-4-input']")));
            input2.sendKeys("Delhi");
            input2.sendKeys(Keys.ENTER);  
        } catch (Exception e) {
            e.printStackTrace();
        }
        
        WebElement objt17 = driver.findElement(By.id("submit"));
        objt17.click();
        
        WebElement objt18 = driver.findElement(By.id("closeLargeModal"));
        objt18.click(); 
        */
        
   
        /////////////////////////////////////////////////////////////////////////////////////////////////////////////  

        /*BOOK STORE (5) 
        WebElement obj4 = driver.findElement(By.xpath("//span[text()='Book Store']"));
        JavascriptExecutor jsExecutor = (JavascriptExecutor) driver;
        jsExecutor.executeScript("arguments[0].click();", obj4);
        
        WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(10));
        WebElement obj8 = wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("searchBox")));
        obj8.sendKeys("Understanding ECMAScript 6");

        WebElement link = driver.findElement(By.linkText("Understanding ECMAScript 6"));
        link.click();
        
        String mainWindowHandle = driver.getWindowHandle();  // Obtener ventana actual
        WebElement linkElement = driver.findElement(By.id("userName-value"));
        String url = linkElement.getText();
        JavascriptExecutor jsExecutor1 = (JavascriptExecutor) driver; //nueva ventana
        jsExecutor1.executeScript("window.open(arguments[0]);", url); //nueva ventana
        Thread.sleep(3000);
        Set<String> allWindowHandles = driver.getWindowHandles();
        String newWindowHandle = "";
        for (String handle : allWindowHandles) { // Encuentra la ventana nueva
            if (!handle.equals(mainWindowHandle)) {
                newWindowHandle = handle;
                break;
            }
        }
        driver.switchTo().window(newWindowHandle);
        driver.close();
        driver.switchTo().window(mainWindowHandle); 
        
        WebElement obj9 = driver.findElement(By.id("addNewRecordButton"));
        obj9.click();
        */
	}	
}