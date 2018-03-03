---
title: "Как: запись в двоичный файл (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- binary files, writing in C++
- files [C++], binary
ms.assetid: 35d97ee6-fc7e-4c36-be18-8bbb3b44b3ae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 66d4c46fa82713e55ce39880f5e379cafcdf9ec6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-write-a-binary-file-ccli"></a>Практическое руководство. Запись в двоичный файл (C++/CLI)
В следующем примере кода демонстрируется записи двоичных данных в файл. Два класса из <xref:System.IO> используются пространство имен: <xref:System.IO.FileStream> и <xref:System.IO.BinaryWriter>. <xref:System.IO.FileStream>представляет фактический файл, пока <xref:System.IO.BinaryWriter> предоставляет интерфейс для потока, который разрешает двоичный доступ.  
  
 Следующий пример кода записывает файл, содержащий целые числа в двоичном формате. Этот файл может быть считан с кодом в [как: чтение двоичного файла (C + +/ CLI)](../dotnet/how-to-read-a-binary-file-cpp-cli.md).  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также  
 [Файловый и потоковый ввод-вывод](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)