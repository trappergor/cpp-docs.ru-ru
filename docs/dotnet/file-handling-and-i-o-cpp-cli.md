---
title: Работы с файлами и ввод вывод (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .NET Framework [C++], file handling
- files [C++], .NET Framework and
- I/O [C++], .NET Framework applications
- .NET Framework [C++], I/O
- files [C++], listing files
- directories [C++], listing files
- monitoring file system events
- FileSystemWatcher class, examples
- examples [C++], monitoring file system changes
- events [C++], monitoring
- file system events [C++]
- files [C++], binary
- binary files, reading in C++
- reading text files
- text files, reading
- files [C++], retrieving information about
- FileInfo class
- binary files, writing in C++
- files [C++], binary
- files [C++], text
- text files, writing in C++
ms.assetid: 3296fd59-a83a-40d4-bd4a-6096cc13101b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 78bfdcc4ea0e73fa27b05c1c043e5f8d6eeb5e00
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693139"
---
# <a name="file-handling-and-io-ccli"></a>Функции работы с файлами и операции ввода-вывода (C++/CLI)
Демонстрирует различные операции с файлами с помощью .NET Framework.  
  
 В следующих разделах описывается использование классов, определенных в <xref:System.IO> пространство имен для выполнения различных операций с файлами.  
  
## <a name="enumerate"></a> Перечисление файлов в каталоге
В следующем примере кода показано, как получить список файлов в каталоге. Кроме того подкаталоги пронумеровываются. В следующем примере кода используется <xref:System.IO.Directory.GetFiles%2A> <xref:System.IO.Directory.GetFiles%2A> и <xref:System.IO.Directory.GetDirectories%2A> методов, чтобы отобразить содержимое каталога C:\Windows.  
  
### <a name="example"></a>Пример  
  
```cpp  
// enum_files.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   String^ folder = "C:\\";  
   array<String^>^ dir = Directory::GetDirectories( folder );  
   Console::WriteLine("--== Directories inside '{0}' ==--", folder);  
   for (int i=0; i<dir->Length; i++)  
      Console::WriteLine(dir[i]);  
  
   array<String^>^ file = Directory::GetFiles( folder );  
   Console::WriteLine("--== Files inside '{0}' ==--", folder);  
   for (int i=0; i<file->Length; i++)  
      Console::WriteLine(file[i]);  
  
   return 0;  
}  
```  

## <a name="monitor"></a> Монитор изменений в файловой системе
В следующем примере кода используется <xref:System.IO.FileSystemWatcher> для регистрации событий, соответствующие файлы, созданные, измененные, удаленные или переименован. Вместо периодического опроса поиск изменений в файлах в каталоге, вы можете использовать <xref:System.IO.FileSystemWatcher> класс, который создает события при обнаружении изменения.  
  
### <a name="example"></a>Пример  
  
```cpp  
// monitor_fs.cpp  
// compile with: /clr  
#using <system.dll>  
  
using namespace System;  
using namespace System::IO;  
  
ref class FSEventHandler  
{  
public:  
    void OnChanged (Object^ source, FileSystemEventArgs^ e)  
    {  
        Console::WriteLine("File: {0} {1}",   
               e->FullPath, e->ChangeType);  
    }  
    void OnRenamed(Object^ source, RenamedEventArgs^ e)  
    {  
        Console::WriteLine("File: {0} renamed to {1}",   
                e->OldFullPath, e->FullPath);  
    }  
};  
  
int main()  
{  
   array<String^>^ args = Environment::GetCommandLineArgs();  
  
   if(args->Length < 2)  
   {  
      Console::WriteLine("Usage: Watcher.exe <directory>");  
      return -1;  
   }  
  
   FileSystemWatcher^ fsWatcher = gcnew FileSystemWatcher( );  
   fsWatcher->Path = args[1];  
   fsWatcher->NotifyFilter = static_cast<NotifyFilters>   
              (NotifyFilters::FileName |   
               NotifyFilters::Attributes |   
               NotifyFilters::LastAccess |   
               NotifyFilters::LastWrite |   
               NotifyFilters::Security |   
               NotifyFilters::Size );  
  
    FSEventHandler^ handler = gcnew FSEventHandler();   
    fsWatcher->Changed += gcnew FileSystemEventHandler(   
            handler, &FSEventHandler::OnChanged);  
    fsWatcher->Created += gcnew FileSystemEventHandler(   
            handler, &FSEventHandler::OnChanged);  
    fsWatcher->Deleted += gcnew FileSystemEventHandler(   
            handler, &FSEventHandler::OnChanged);  
    fsWatcher->Renamed += gcnew RenamedEventHandler(   
            handler, &FSEventHandler::OnRenamed);  
  
    fsWatcher->EnableRaisingEvents = true;  
  
    Console::WriteLine("Press Enter to quit the sample.");  
    Console::ReadLine( );  
}  
```  

## <a name="read_binary"></a> Прочитать двоичный файл
В следующем примере кода демонстрируется чтение двоичных данных из файла, используя два класса из <xref:System.IO?displayProperty=fullName> пространство имен: <xref:System.IO.FileStream> и <xref:System.IO.BinaryReader>. <xref:System.IO.FileStream> представляет фактический файл. <xref:System.IO.BinaryReader> предоставляет интерфейс для потока, который разрешает двоичный доступ.  
  
 В примере кода считывает файл с именем data.bin и содержит целые числа в двоичном формате. Сведения об этом файле см. в разделе [как: запись в двоичный файл (C + +/ CLI)](../dotnet/how-to-write-a-binary-file-cpp-cli.md).  
  
### <a name="example"></a>Пример  
  
```cpp  
// binary_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()   
{  
   String^ fileName = "data.bin";  
   try  
   {  
      FileStream^ fs = gcnew FileStream(fileName, FileMode::Open);  
      BinaryReader^ br = gcnew BinaryReader(fs);  
  
      Console::WriteLine("contents of {0}:", fileName);  
      while (br->BaseStream->Position < br->BaseStream->Length)  
         Console::WriteLine(br->ReadInt32().ToString());  
  
      fs->Close( );  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("File '{0}' not found", fileName);  
      else  
         Console::WriteLine("Exception: ({0})", e);  
      return -1;  
   }  
   return 0;  
}  
```  
## <a name="read_text"></a> Чтение из текстового файла
В следующем примере кода показано, как открыть и прочитать текст файла по одной строке за раз, с помощью <xref:System.IO.StreamReader> класс, который определен в <xref:System.IO?displayProperty=fullName> пространства имен. Экземпляр этого класса используется для открытия текстового файла и затем <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName> метод используется для считывания каждой строки.  
  
 Данный пример кода считывает файл с именем textfile.txt и содержит текст. Сведения об этом файле см. в разделе [как: запись в текстовый файл (C + +/ CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md).  
  
### <a name="example"></a>Пример  
  
```cpp  
// text_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   String^ fileName = "textfile.txt";  
   try   
   {  
      Console::WriteLine("trying to open file {0}...", fileName);  
      StreamReader^ din = File::OpenText(fileName);  
  
      String^ str;  
      int count = 0;  
      while ((str = din->ReadLine()) != nullptr)   
      {  
         count++;  
         Console::WriteLine("line {0}: {1}", count, str );  
      }  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("file '{0}' not found", fileName);  
      else  
         Console::WriteLine("problem reading file '{0}'", fileName);  
   }  
  
   return 0;  
}  
```  

## <a name="retrieve"></a> Получение сведений о файле 
В следующем примере кода показано <xref:System.IO.FileInfo> класса. Если имя файла, этот класс можно использовать для получения сведений о файле, такие как размер файла, каталога, полное имя и Дата и время создания и последнего изменения.  
  
 Этот код извлекает информацию о файлах для Notepad.exe.  
  
### <a name="example"></a>Пример  
  
```cpp  
// file_info.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   array<String^>^ args = Environment::GetCommandLineArgs();  
   if (args->Length < 2)  
   {  
      Console::WriteLine("\nUSAGE : file_info <filename>\n\n");  
      return -1;  
   }  
  
   FileInfo^ fi = gcnew FileInfo( args[1] );  
  
   Console::WriteLine("file size: {0}", fi->Length );  
  
   Console::Write("File creation date:  ");  
   Console::Write(fi->CreationTime.Month.ToString());  
   Console::Write(".{0}", fi->CreationTime.Day.ToString());  
   Console::WriteLine(".{0}", fi->CreationTime.Year.ToString());  
  
   Console::Write("Last access date:  ");  
   Console::Write(fi->LastAccessTime.Month.ToString());  
   Console::Write(".{0}", fi->LastAccessTime.Day.ToString());  
   Console::WriteLine(".{0}", fi->LastAccessTime.Year.ToString());  
  
   return 0;  
}  
```  

## <a name="write_binary"></a> Запись в двоичный файл
В следующем примере кода демонстрируется запись двоичных данных в файл. Два класса из <xref:System.IO> используются пространства имен: <xref:System.IO.FileStream> и <xref:System.IO.BinaryWriter>. <xref:System.IO.FileStream> представляет фактический файл, хотя <xref:System.IO.BinaryWriter> предоставляет интерфейс для потока, который разрешает двоичный доступ.  
  
 В следующем примере кода записывает файл, содержащий целые числа в двоичном формате. Этот файл может быть считан с код в [как: чтение двоичного файла (C + +/ CLI)](../dotnet/how-to-read-a-binary-file-cpp-cli.md).  
  
### <a name="example"></a>Пример  
  
```cpp  
// binary_write.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   array<Int32>^ data = {1, 2, 3, 10000};  
  
   FileStream^ fs = gcnew FileStream("data.bin", FileMode::Create);  
   BinaryWriter^ w = gcnew BinaryWriter(fs);  
  
   try   
   {  
      Console::WriteLine("writing data to file:");  
      for (int i=0; i<data->Length; i++)  
      {  
         Console::WriteLine(data[i]);  
         w->Write(data[i]);  
      }  
   }  
   catch (Exception^)   
   {  
     Console::WriteLine("data could not be written");  
     fs->Close();  
     return -1;  
   }  
  
   fs->Close();  
   return 0;  
}  
```  

## <a name="write_text"></a> Запись в текстовый файл
В следующем примере кода показано, как для создания текстового файла и запись в него с помощью текста <xref:System.IO.StreamWriter> класс, который определен в <xref:System.IO> пространства имен. <xref:System.IO.StreamWriter> Конструктор принимает имя создаваемого файла. Если файл существует, он перезаписывается (Если передается значение false как второй <xref:System.IO.StringWriter> аргумент конструктора).  
  
 Файл реализуется с помощью <xref:System.IO.StreamWriter.Write%2A> и <xref:System.IO.TextWriter.WriteLine%2A> функции.  
  
### <a name="example"></a>Пример  
  
```cpp  
// text_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()   
{  
   String^ fileName = "textfile.txt";  
  
   StreamWriter^ sw = gcnew StreamWriter(fileName);  
   sw->WriteLine("A text file is born!");  
   sw->Write("You can use WriteLine");  
   sw->WriteLine("...or just Write");  
   sw->WriteLine("and do {0} output too.", "formatted");  
   sw->WriteLine("You can also send non-text objects:");  
   sw->WriteLine(DateTime::Now);  
   sw->Close();  
   Console::WriteLine("a new file ('{0}') has been written", fileName);  
  
   return 0;  
}  
```  

## <a name="see-also"></a>См. также   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

 [Файловый и потоковый ввод-вывод](/dotnet/standard/io/index)

 [Пространство имен System.IO](https://msdn.microsoft.com/library/system.io.aspx)