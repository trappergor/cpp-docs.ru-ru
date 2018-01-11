---
title: "Как: чтение данных из реестра Windows (C + +/ CLI) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++, reading from Windows Registry
- registry, reading
ms.assetid: aebf52c0-acc7-40e2-adbc-d34e0a1e467e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dfb654ba2cce069086713322624e947e14bc26f4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-read-data-from-the-windows-registry-ccli"></a>Практическое руководство. Чтение данных из реестра Windows (C++/CLI)
Следующий пример кода использует <xref:Microsoft.Win32.Registry.CurrentUser> ключ для чтения данных из реестра Windows. Во-первых, выполняется перечисление подразделов с помощью <xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A> открывается с помощью метода, а затем подраздел удостоверения <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> метод. Как и корневые ключи, каждый подраздел представлен <xref:Microsoft.Win32.RegistryKey> класса. Наконец, новый <xref:Microsoft.Win32.RegistryKey> объект используется для перечисления пар "ключ значение".  
  
## <a name="example"></a>Пример  
  
### <a name="code"></a>Код  
  
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
  
## <a name="remarks"></a>Примечания  
 <xref:Microsoft.Win32.Registry> Класс является контейнером для статических экземпляров <xref:Microsoft.Win32.RegistryKey>. Каждый экземпляр представляет корневой узел реестра. Экземпляры <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine>, и <xref:Microsoft.Win32.Registry.Users>.  
  
 В дополнение к, статическим, объекты внутри <xref:Microsoft.Win32.Registry> класса доступны только для чтения. Кроме того, экземпляры из <xref:Microsoft.Win32.RegistryKey> объектов класса, которые создаются для доступа к содержимому реестра, также доступны только для чтения. Пример переопределения этого поведения см. в разделе [как: записывать данные в реестре Windows (C + +/ CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md).  
  
 Существует два дополнительных объектов в <xref:Microsoft.Win32.Registry> класса: <xref:Microsoft.Win32.Registry.DynData> и <xref:Microsoft.Win32.Registry.PerformanceData>. Оба являются экземплярами <xref:Microsoft.Win32.RegistryKey> класса. <xref:Microsoft.Win32.Registry.DynData> Объект содержит динамические сведения реестра, который поддерживается только в Windows 98 и Windows Me. <xref:Microsoft.Win32.Registry.PerformanceData> Объект можно использовать для доступа к данным счетчиков производительности для приложений, использующих систему мониторинга производительности Windows. <xref:Microsoft.Win32.Registry.PerformanceData> Узел представляет сведения, которые в действительности не хранятся в реестре и поэтому нельзя просмотреть с помощью Regedit.exe.  
  
## <a name="see-also"></a>См. также  
 [Как: запись данных в реестр Windows (C + +/ CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)   
 [Операции Windows (C + +/ CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [Программирование .NET с использованием C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)