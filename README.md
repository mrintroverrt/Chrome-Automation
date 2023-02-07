# Chrome-Automation
This Code Writed For Automate the Chrome Browser In Android Appium Use Oppo Mobile 

package org.inmakestest;

import java.awt.AWTException;
import java.net.MalformedURLException;
import java.net.URL;

import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.remote.DesiredCapabilities;

import io.appium.java_client.android.AndroidDriver;

public class FirstTest {
	public static AndroidDriver driver;

	public static void main(String[] args) throws MalformedURLException, InterruptedException, AWTException {

		DesiredCapabilities cap = new DesiredCapabilities();

		cap.setCapability("platformName", "Android");
		cap.setCapability("platformVersion", "9");
		cap.setCapability("noReset", true);
		cap.setCapability("deviceName", "OPPO A31");
		cap.setCapability("udid", "EQEMCQ4PHISGJFOB");
		cap.setCapability("appPackage", "com.android.chrome");
		cap.setCapability("appActivity", "com.google.android.apps.chrome.Main");
		cap.setCapability("unicodeKeyboard", true);
		cap.setCapability("resetKeyboard", true);

		URL url = new URL("http://0.0.0.0:4723/wd/hub");
		driver = new AndroidDriver(url, cap);

		driver.findElement(By.id("com.android.chrome:id/home_button")).click();
		Thread.sleep(3000);
		driver.findElement(By.id("com.android.chrome:id/search_box_text")).click();
		Thread.sleep(3000);
		WebElement srcbar = driver.findElement(By.id("com.android.chrome:id/url_bar"));
		srcbar.sendKeys("Flipkart ");
		Actions action = new Actions(driver);
		action.sendKeys(Keys.ENTER).perform();
		Thread.sleep(3000);
		driver.findElement(By.xpath(
				"//android.view.View[@content-desc=\"Flipkart https://www.flipkart.com Flipkart\"]/android.view.View[2]"))
				.click();
		Thread.sleep(6000);
		driver.findElement(By.xpath(
				"/hierarchy/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.view.ViewGroup/android.widget.FrameLayout[1]/android.widget.FrameLayout[1]/android.webkit.WebView/android.view.View/android.view.View/android.view.View/android.view.View/android.view.View[2]/android.view.View[2]/android.view.View/android.view.View/android.view.View/android.view.View/android.view.View/android.view.View/android.widget.TextView"))
				.click();
		Thread.sleep(6000);
		WebElement flpsrc = driver.findElement(By.xpath(
				"/hierarchy/android.widget.FrameLayout/android.widget.LinearLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.widget.FrameLayout/android.view.ViewGroup/android.widget.FrameLayout[1]/android.widget.FrameLayout[1]/android.webkit.WebView/android.view.View/android.view.View/android.view.View/android.view.View[1]/android.widget.EditText"));
		flpsrc.sendKeys("IPhone");
		Thread.sleep(3000);
		Actions a = new Actions(driver);
		a.sendKeys(Keys.ENTER).perform();
	}

}

