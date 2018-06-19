---
title: 'Как: запись в двоичный файл (C + +/ CLI) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- binary files, writing in C++
- files [C++], binary
ms.assetid: 35d97ee6-fc7e-4c36-be18-8bbb3b44b3ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 69467b913ea76b5f5e19772ee7d0d846a363c5e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130131"
---
# <a name="how-to-write-a-binary-file-ccli"></a>Практическое руководство. Запись в двоичный файл (C++/CLI)
В следующем примере кода демонстрируется записи двоичных данных в файл. Два класса из <xref:System.IO> используются пространство имен: <xref:System.IO.FileStream> и <xref:System.IO.BinaryWriter>. <xref:System.IO.FileStream> представляет фактический файл, пока <xref:System.IO.BinaryWriter> предоставляет интерфейс для потока, который разрешает двоичный доступ.  
  
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