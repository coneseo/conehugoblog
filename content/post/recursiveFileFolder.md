+++
title = "recusiveFileFolder"
date = "20181221"
+++

```
package my.examples.ioexam;

import java.io.File;
import java.io.FileInputStream;

public class IOexam01 {
    public static void main(String[] args) {
        //윈도우 사용자 c:\tmp 폴더를 만든다. 맥 사용자는 \tmp 폴더를 사용한다.
        // 임의의 폴더를 만들고, 그 안에 몇가지 폴더를 만든다.
        //내 문서에 examples 만들었다. C:\Users\woon4\Documents\examplefolder\com\examples
        //1.위의 폴더가 있는지 없는지 검사한다. 있으면 있다. 없으면 없다고 출력
        //2.해당경로가 파일인지, 폴더인지를 검사한다. 파일이면 파일, 폴더면 폴더로 출력
        //3.해당 경로에 어떤 파일과 폴더들이 있는지 정보를 출력
        //4. IOExam02를 만들고, PATH를 지정하면 폴더일 경우, 해당 폴더 아래의 모든 파일과 폴더정보를 출력하도록 한다. (재귀호출)

        File file = new File("C:\\Users\\woon4\\Documents\\examplefolder\\com\\examples");

        if(file.exists()){
            System.out.println(file.getName() + "이 있습니다.");
            if(file.isDirectory()){
                System.out.println("directory입니다.");
                File[] files = file.listFiles();
                for(File f : files){
                    System.out.println(f.getName() +" "+(f.isDirectory() ?  "[DIR]" : "[FILE]"+ f.length()));
                }
            }
        }else{
            System.out.println("없습니다.");
        }

//        if(file.isFile()){
//            System.out.println("file 입니다.");
//        }else if(file.isDirectory()){
//            System.out.println("folder 입니다.");
//        }
    }
}
```

```
package my.examples.ioexam;

import java.io.File;

public class IOexam02 {
    public static void main(String[] args){
        File file = new File("C:\\Users\\woon4\\Documents\\examplefolder\\com\\examples");
        if(file.exists()){
            if(file.isFile()){
                printFile("",file);
            }else{
                printDir("", file);
            }
        }

    }

    public static void printFile(String space, File file){
        System.out.println(space + file.getName());
    }

    public static void printDir(String space, File file){
        System.out.println(space + file.getName() + "[DIR]");
        space = space + "  ";
        File[] files = file.listFiles();
        for(File f : files){
            if(f.isFile()){
                printFile(space, f);
            }else if(f.isDirectory()){
                printDir(space, f);
            }
        }
    }
}
```
