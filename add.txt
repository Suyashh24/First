import java.util.*;
import java.io.*;
class CopyFileContentCaseChange
{
public static void main(String a[]) throws Exception
{
BufferedReader br=new BufferedReader(new InputStreamReader(System.in));
System.out.println("Enter name of the file to copy");
String f1=br.readLine();

System.out.println("Enter destination file name");
String f2=br.readLine();
FileReader fr=new FileReader(f1);
FileWriter fw=new FileWriter(f2);
int ch;
while((ch=fr.read() ) != -1)
{
char ch1=(char)ch;
if(Character.isUpperCase(ch1))
{
ch1=Character.toLowerCase(ch1);
fw.write(ch1);
}
else if(Character.isLowerCase(ch1))
{
ch1=Character.toUpperCase(ch1);
fw.write(ch1);
}
else if(Character.isDigit(ch1))
{
ch1='*';
fw.write(ch1);
}
else if(Character.isSpace(ch1))
{
fw.write(ch1);
}
}
fr.close();
fw.close();
}
}