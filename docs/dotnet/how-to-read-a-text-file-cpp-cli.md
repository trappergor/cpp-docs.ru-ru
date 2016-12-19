---
title: "Практическое руководство. Чтение из текстового файла (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "чтение текстовых файлов"
  - "текстовые файлы, чтение"
ms.assetid: 80551c01-d769-4b6d-8db7-fd53bde21b62
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Чтение из текстового файла (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере кода демонстрируется порядок открытия и построчного прочтения текстового файла с помощью класса <xref:System.IO.StreamReader>, который определен в пространстве имен <xref:System.IO?displayProperty=fullName>.  Экземпляр этого класса используется для открытия текстового файла, а затем для считывания каждой строки используется метод <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName>.  
  
 В этом примере кода считывает файл с именем textfile.txt и содержит текст.  Дополнительные сведения об этом файле см. в разделе [Практическое руководство. Запись данных в текстовый файл](../Topic/How%20to:%20Write%20a%20Text%20File%20\(C++-CLI\).md).  
  
## Пример  
  
```  
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
  
## См. также  
 [Файловый и потоковый ввод\-вывод](../Topic/File%20and%20Stream%20I-O.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)