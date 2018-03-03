---
title: "Как: чтение из текстового файла (C + +/ CLI) | Документы Microsoft"
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
- reading text files
- text files, reading
ms.assetid: 80551c01-d769-4b6d-8db7-fd53bde21b62
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a1924a918d8a3255ca4a8488adc366155c1110dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-read-a-text-file-ccli"></a>Практическое руководство. Чтение из текстового файла (C++/CLI)
В следующем примере кода показано, как для открытия и чтения текстового файла по одной строке за раз с помощью <xref:System.IO.StreamReader> класс, который определен в <xref:System.IO?displayProperty=fullName> пространства имен. Экземпляр этого класса используется для открытия текстового файла и затем <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName> метод используется для считывания каждой строки.  
  
 Данный пример кода считывает файл, который с именем textfile.txt и содержит текст. Сведения о файлы этого типа см. в разделе [как: запись текстового файла (C + +/ CLI)](../dotnet/how-to-write-a-text-file-cpp-cli.md).  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также  
 [Файловый и потоковый ввод-вывод](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)