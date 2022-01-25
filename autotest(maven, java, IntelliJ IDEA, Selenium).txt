import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.devtools.v93.input.Input;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;

import java.time.Duration;

public class Main {
    public static void main(String[] args) {
        System.setProperty("webdriver.chrome.driver","C:\\chromedriver\\chromedriver.exe");
        ChromeDriver driver = new ChromeDriver();

        driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(2));
        WebDriverWait wait = new WebDriverWait(driver, Duration.ofSeconds(2));

        try {
            driver.get("https://cabinet.nalozhka.ru/deals/create");
            Thread.sleep(2000);

            WebElement input1 = driver.findElement(By.xpath("(//input[@data-v-35f52db2])[1]"));
            input1.sendKeys("30");
            WebElement input2 = driver.findElement(By.xpath("(//input[@data-v-35f52db2])[2]"));
            input2.sendKeys("35");
            WebElement input3 = driver.findElement(By.xpath("(//input[@data-v-35f52db2])[3]"));
            input3.sendKeys("32");
            WebElement input4 = driver.findElement(By.xpath("(//input[@data-v-35f52db2])[4]"));
            input4.sendKeys("5");

            WebElement input5 = driver.findElement(By.xpath("(//input[@data-v-35f52db2])[5]"));
            input5.sendKeys("Ваза");
            WebElement input6 = driver.findElement(By.xpath("(//input[@data-v-35f52db2])[6]"));
            input6.sendKeys("1");
            WebElement input7 = driver.findElement(By.xpath("(//input[@data-v-35f52db2])[7]"));
            input7.sendKeys("1000");

            WebElement dubl = driver.findElement(By.xpath("(//a[@class='dotted-menu__toggler'])[2]"));
            dubl.click();
            WebElement dubl2 = driver.findElement(By.xpath("(//a[@class='dotted-menu__item dotted-menu__item_link'])[2]"));
            dubl2.click();

            WebElement checkbox = driver.findElement(By.xpath("//span[@class='create-deal__add']"));
            checkbox.click();

            WebElement input8 = driver.findElement(By.xpath("(//input[@data-v-35f52db2])[11]"));
            input8.sendKeys("Пирог");
            WebElement input9 = driver.findElement(By.xpath("(//input[@data-v-35f52db2])[12]"));
            input9.sendKeys("2");
            WebElement input10 = driver.findElement(By.xpath("(//input[@data-v-35f52db2])[13]"));
            input10.sendKeys("2000");
            

            WebElement gorod1 = driver.findElement(By.xpath("(//input[@autocomplete='off'])[1]"));
            gorod1.sendKeys("Пенза");
            WebElement pena = (new WebDriverWait(driver, Duration.ofSeconds(5))
                    .until(ExpectedConditions.presenceOfElementLocated(By.xpath("(//div[@class='item selected'])[1]"))));
            pena.click();
            WebElement gorod2 = driver.findElement(By.xpath("(//input[@autocomplete='off'])[2]"));
            gorod2.sendKeys("Белебей");
            WebElement belebey = (new WebDriverWait(driver, Duration.ofSeconds(5))
                    .until(ExpectedConditions.presenceOfElementLocated(By.xpath("(//div[@class='item selected'])[2]"))));
            belebey.click();

            WebElement tarif = (new WebDriverWait(driver, Duration.ofSeconds(20))
                    .until(ExpectedConditions.presenceOfElementLocated(By.xpath("(//a[@class='tariff__item'])[1]"))));
            tarif.click();

            WebElement page = driver.findElement(By.xpath("//button[@class='button button_size-64 button_no-shadow button_no-transform save-changes__button']"));
            page.click();
            Thread.sleep(2000);



            WebElement page2 = driver.findElement(By.xpath("//button[@class='button button_size-50 button_radius-2']"));
            page2.click();

            WebElement page3 = driver.findElement(By.xpath("//button[@class='button button_size-64 button_no-shadow button_no-transform save-changes__button']"));
            page3.click();
            Thread.sleep(2000);

            WebElement comment = driver.findElement(By.xpath("//textarea[@class='input__field']"));
            comment.sendKeys("Просто оставляем комментарий");

            WebElement upload = driver.findElement(By.xpath("//input[@class='file__input']"));
            upload.sendKeys("C:\\test.jpg"); //Указать, поменять путь к изображению


        } catch (InterruptedException e) {
            e.printStackTrace();
        }


    }

}
