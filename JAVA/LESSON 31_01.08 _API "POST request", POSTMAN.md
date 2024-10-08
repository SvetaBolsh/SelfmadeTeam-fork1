## TEAMWORK
1. Send a POST request (public ResultItem sendItem(Item item))
2. You should send one object and receive a different object with different data
3. Test it out POSTMAN
   

```java
package com.datorium.Datorium.API;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.*;

import java.util.ArrayList;

@SpringBootApplication
@RestController
@CrossOrigin
public class DatoriumApiApplication {

	public static void main(String[] args) {
		SpringApplication.run(DatoriumApiApplication.class, args);
	}

	@PostMapping("/joke")
	public String joke(@RequestBody Developer developer) {
		if (developer.programmingLanguage.equals("java") && developer.wearGlasses.equals("yes")) {
			var language= new Language();
			language.language = developer.programmingLanguage.toUpperCase();
           	 return String.format("Why do %s developers wear glasses?\nBecause they can't C#. 😉", language.language );
		}
		return "No joke for you! 😜";
	}
}
```

Language.java
```java
package com.datorium.Datorium.API;

public class Language {
    public String language;
}
```

Developer.java
```java
package com.datorium.Datorium.API;

public class Developer {
    public String programmingLanguage;
    public String wearGlasses;
}
```

Postman:

<img width="644" alt="Screenshot 2024-08-02 at 16 40 17" src="https://github.com/user-attachments/assets/7fa5a392-897f-44ec-9db9-cb329723394e">

<img width="640" alt="Screenshot 2024-08-02 at 16 39 42" src="https://github.com/user-attachments/assets/11f43ec0-60d0-4acf-bd58-100d8f5d8048">


