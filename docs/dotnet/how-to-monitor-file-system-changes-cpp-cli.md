---
title: "Как: отслеживание изменений в файловой системе (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- monitoring file system events
- FileSystemWatcher class, examples
- examples [C++], monitoring file system changes
- events [C++], monitoring
- file system events [C++]
ms.assetid: 207a3069-e63d-417e-8b56-00ab44f29c52
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7b0b75ea559cac35ef764818d3a99162a72cfc62
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-monitor-file-system-changes-ccli"></a>Практическое руководство. Отслеживание изменений в файловой системе (C++/CLI)
Следующий пример кода использует <xref:System.IO.FileSystemWatcher> для регистрации событий, соответствующие файлам, которые созданы, изменены, удален или переименован. Вместо периодически анализировать каталог на предмет изменений в файлах, можно использовать <xref:System.IO.FileSystemWatcher> класса для вызова событий при обнаружении изменений.  
  
## <a name="example"></a>Пример  
  
```  
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
  
## <a name="see-also"></a>См. также  
 [System.IO-пространство имен](https://msdn.microsoft.com/en-us/library/system.io.aspx)   
 [Файловый и потоковый ввод-вывод](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)