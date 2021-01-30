# Maven---read-file

## File in resource folder : data.txt

```java
package com.cozla;

import java.io.File;
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.util.List;

public class Runner {

    public static final String FILENAME = "data.txt";

    public static void main(String[] args) throws IOException {

        ClassLoader classLoader = Runner.class.getClassLoader();

        File file = new File(classLoader.getResource(FILENAME).getFile());

        List<String> lines = Files.readAllLines(file.toPath(), StandardCharsets.UTF_8);

        for (String line: lines) {
            System.out.println(line);
        }

    }

}
```
