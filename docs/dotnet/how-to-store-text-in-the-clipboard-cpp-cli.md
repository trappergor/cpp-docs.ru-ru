---
title: "Практическое руководство. Хранение текста в буфере обмена (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "буфер обмена, сохранение текста"
  - "текст, хранение в Clipboard"
ms.assetid: 9996023f-b700-47ad-8ad9-1ba201eaa5a6
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Хранение текста в буфере обмена (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере кода используется объект <xref:System.Windows.Forms.Clipboard>, определенный в пространстве имен <xref:System.Windows.Forms> для хранения строки.  Это объект предоставляет две функции\-члена: <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> и <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>.  Данные хранятся в буфере обмена посредством отправки любого объекта, производного от <xref:System.Object>, в <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>.  
  
## Пример  
  
```  
// store_clipboard.cpp  
// compile with: /clr  
#using <System.dll>  
#using <System.Drawing.dll>  
#using <System.Windows.Forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
  
[STAThread] int main()  
{  
   String^ str = "This text is copied into the Clipboard.";  
  
   // Use 'true' as the second argument if  
   // the data is to remain in the clipboard  
   // after the program terminates.  
   Clipboard::SetDataObject(str, true);  
  
   Console::WriteLine("Added text to the Clipboard.");  
  
   return 0;  
}  
```  
  
## См. также  
 [Практическое руководство. Извлечение текста из буфера обмена](../Topic/How%20to:%20Retrieve%20Text%20from%20the%20Clipboard%20\(C++-CLI\).md)   
 [Операции Windows](../dotnet/windows-operations-cpp-cli.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)