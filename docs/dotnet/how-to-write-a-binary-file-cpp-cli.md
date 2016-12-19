---
title: "Практическое руководство. Запись в двоичный файл (C++/CLI) | Microsoft Docs"
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
  - "двоичные файлы, запись в C++"
  - "файлы [C++], двоичные"
ms.assetid: 35d97ee6-fc7e-4c36-be18-8bbb3b44b3ae
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Запись в двоичный файл (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере описывается порядок записи двоичных данных в файл.  Используются два класса из пространства имен <xref:System.IO>: <xref:System.IO.FileStream> и <xref:System.IO.BinaryWriter>.  Класс <xref:System.IO.FileStream> представляет фактический файл, а класс <xref:System.IO.BinaryWriter> — интерфейс потока, обеспечивающего двоичный доступ.  
  
 В следующем примере выполняется запись данных в файл, содержащий целые числа в двоичном формате.  Описание порядка чтения данных из этого файла см. в разделе [Практическое руководство. Чтение данных из двоичного файла](../Topic/How%20to:%20Read%20a%20Binary%20File%20\(C++-CLI\).md).  
  
## Пример  
  
```  
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
  
## См. также  
 [Файловый и потоковый ввод\-вывод](../Topic/File%20and%20Stream%20I-O.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)