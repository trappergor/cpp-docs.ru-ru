---
title: "Практическое руководство. Запись данных в реестр Windows (C++/CLI) | Microsoft Docs"
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
  - "реестр, запись в"
  - "Visual C++, запись в регистр Windows"
ms.assetid: 3d40b978-4baa-4779-bfe3-47e2917b757f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Запись данных в реестр Windows (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере используется ключ <xref:Microsoft.Win32.Registry.CurrentUser> для создания доступного для записи экземпляра класса <xref:Microsoft.Win32.RegistryKey>, соответствующего разделу **Software**.  Затем с помощью метода <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A> создается новый раздел и добавляются пары "ключ\-значение".  
  
## Пример  
  
### Код  
  
```  
// registry_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main()  
{  
   // The second OpenSubKey argument indicates that  
   // the subkey should be writable.   
   RegistryKey^ rk;  
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);  
   if (!rk)  
   {  
      Console::WriteLine("Failed to open CurrentUser/Software key");  
      return -1;  
   }  
  
   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");  
   if (!nk)  
   {  
      Console::WriteLine("Failed to create 'NewRegKey'");  
      return -1;  
   }  
  
   String^ newValue = "NewValue";  
   try  
   {  
      nk->SetValue("NewKey", newValue);  
      nk->SetValue("NewKey2", 44);  
   }  
   catch (Exception^)  
   {  
      Console::WriteLine("Failed to set new values in 'NewRegKey'");  
      return -1;  
   }  
  
   Console::WriteLine("New key created.");  
   Console::Write("Use REGEDIT.EXE to verify ");  
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");  
   return 0;  
}  
```  
  
## Примечания  
 В платформе .NET Framework для обращения к реестру используются классы <xref:Microsoft.Win32.Registry> и [RegistryKey](https://msdn.microsoft.com/en-us/library/microsoft.win32.registrykey.aspx), определенные в пространстве имен <xref:Microsoft.Win32>.  Класс **Registry** представляет собой контейнер статических экземпляров класса <xref:Microsoft.Win32.RegistryKey>.  Каждый экземпляр представляет корневой узел реестра.  К этим экземплярам относятся <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> и <xref:Microsoft.Win32.Registry.Users>.  
  
## См. также  
 [Практическое руководство. Чтение данных из реестра Windows](../dotnet/how-to-read-data-from-the-windows-registry-cpp-cli.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)