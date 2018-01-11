---
title: "Как: чтение двоичного файла (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- files [C++], binary
- binary files, reading in C++
ms.assetid: 41ad9ad1-5cac-489c-874e-4bb3a649073a
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3714ba3df6d44559db66b56ea1a0f8a3ff7f3f44
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-read-a-binary-file-ccli"></a>Практическое руководство. Чтение данных из двоичного файла (C++/CLI)
В следующем примере кода показано, как считывать двоичные данные из файла, с помощью двух классов из <xref:System.IO?displayProperty=fullName> пространство имен: <xref:System.IO.FileStream> и <xref:System.IO.BinaryReader>. <xref:System.IO.FileStream>представляет фактический файл. <xref:System.IO.BinaryReader>предоставляет интерфейс для потока, который разрешает двоичный доступ.  
  
 Пример кода считывает файл, который назван data.bin и содержит целые числа в двоичном формате. Сведения о файлы этого типа см. в разделе [как: запись в двоичный файл (C + +/ CLI)](../dotnet/how-to-write-a-binary-file-cpp-cli.md).  
  
## <a name="example"></a>Пример  
  
```  
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
  
## <a name="see-also"></a>См. также  
 [Файловый и потоковый ввод-вывод](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)