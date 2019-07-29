import java.io.BufferedReader;
import java.io.BufferedWriter;
import java.io.File;
import java.io.FileWriter;
import java.io.IOException;
import java.io.InputStream;
import java.io.InputStreamReader;
import java.net.MalformedURLException;
import java.net.URL;

public class javaTraining {

    public static void main(String[] args) {        
        downloadContent();
    }

    public static void downloadContent() {
        URL url = null;
        InputStream stream = null;
        try {
            url = new URL("https://www.sap.com/belgique/index.html");
            stream = url.openStream();
            BufferedReader input = new BufferedReader(new InputStreamReader(stream));
            File file = new File("data.html");
            // Creating file if not existing.
            if (!file.exists()) {
                file.createNewFile();
            }
            BufferedWriter output = new BufferedWriter(new FileWriter(file.getAbsoluteFile()));
            String line;
            while ((line = input.readLine()) != null) {
                output.write(line.replace("SAP", "Jarmak"));
            }
            output.close();
        }
        catch (MalformedURLException ue) {
            ue.printStackTrace();
        }
        catch (IOException ie) {
            ie.printStackTrace();
        }
        try {
            if (stream != null)
                stream.close();
        } catch (IOException ie) {
            ie.printStackTrace();
        }
    }

}
