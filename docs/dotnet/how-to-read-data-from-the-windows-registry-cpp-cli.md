---
title: "Практическое руководство. Чтение данных из реестра Windows (C++/CLI) | Microsoft Docs"
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
  - "реестр, чтение"
  - "Visual C++, чтение из регистра Windows"
ms.assetid: aebf52c0-acc7-40e2-adbc-d34e0a1e467e
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Чтение данных из реестра Windows (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующем примере для чтения данных из реестра Windows кода используется ключ <xref:Microsoft.Win32.Registry.CurrentUser>.  Сначала выполняется перечисление подразделов с помощью метода <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A>, а затем подраздел Identities \(Идентификаторы\) открывается с помощью метода <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A>.  Как и корневые ключи, каждый подраздел представлен классом <xref:Microsoft.Win32.RegistryKey>.  И в завершение, новый объект <xref:Microsoft.Win32.RegistryKey> используется для перечисления пар ключ\-значение.  
  
## Пример  
  
### Код  
  
```  
// registry_read.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main( )  
{  
   array<String^>^ key = Registry::CurrentUser->GetSubKeyNames( );  
  
   Console::WriteLine("Subkeys within CurrentUser root key:");  
   for (int i=0; i<key->Length; i++)  
   {  
      Console::WriteLine("   {0}", key[i]);  
   }  
  
   Console::WriteLine("Opening subkey 'Identities'...");  
   RegistryKey^ rk = nullptr;  
   rk = Registry::CurrentUser->OpenSubKey("Identities");  
   if (rk==nullptr)  
   {  
      Console::WriteLine("Registry key not found - aborting");  
      return -1;  
   }  
  
   Console::WriteLine("Key/value pairs within 'Identities' key:");  
   array<String^>^ name = rk->GetValueNames( );  
   for (int i=0; i<name->Length; i++)  
   {  
      String^ value = rk->GetValue(name[i])->ToString();  
      Console::WriteLine("   {0} = {1}", name[i], value);  
   }  
  
   return 0;  
}  
```  
  
## Примечания  
 Класс <xref:Microsoft.Win32.Registry> является контейнером для статических экземпляров класса <xref:Microsoft.Win32.RegistryKey>.  Каждый экземпляр представляет корневой узел реестра.  К этим экземплярам относятся <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> и <xref:Microsoft.Win32.Registry.Users>.  
  
 Помимо статического свойства, объекты в классе <xref:Microsoft.Win32.Registry> доступны только для чтения.  Кроме того, экземпляры класса <xref:Microsoft.Win32.RegistryKey>, которые создаются для доступа к содержимому объектов реестра, также доступны только для чтения.  Пример переопределения данного поведения см. в разделе [Практическое руководство. Запись данных в реестр Windows](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md).  
  
 В классе <xref:Microsoft.Win32.Registry> находятся два дополнительных объекта: <xref:Microsoft.Win32.Registry.DynData> и <xref:Microsoft.Win32.Registry.PerformanceData>.  Оба экземпляра принадлежат классу <xref:Microsoft.Win32.RegistryKey>.  Объект <xref:Microsoft.Win32.Registry.DynData> содержит динамические сведения реестра, которые поддерживаются только операционными системами Windows 98 и Windows Me.  Объект <xref:Microsoft.Win32.Registry.PerformanceData> может использоваться для доступа к данным счетчиков производительности для приложений, использующих "Систему мониторинга производительности Windows".  узел <xref:Microsoft.Win32.Registry.PerformanceData> представляет сведения, которые фактически не сохраняются в реестре, и, следовательно, не могут быть отображены с помощью приложения REGEDIT.  
  
## См. также  
 [Практическое руководство. Запись данных в реестр Windows](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)   
 [Операции Windows](../dotnet/windows-operations-cpp-cli.md)   
 [программирование .NET с использованием C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)