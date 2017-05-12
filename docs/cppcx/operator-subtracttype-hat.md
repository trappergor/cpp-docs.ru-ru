---
title: "оператор Type^ | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# оператор Type^
Включает преобразование из [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) в `Platform::Type`.  
  
## Синтаксис  
  
```cpp  
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName)  
```  
  
## Возвращаемое значение  
 Возвращает `Platform::Type` при получении [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx).  
  
## Заметки  
 `TypeName` является независимой от языка структурой среды выполнения Windows для представления сведений о типе.[Platform::Type](../cppcx/platform-type-class.md) используется только в C\+\+ и не передается через двоичный интерфейс приложений \(ABI\). Ниже представлен один из способов использования `TypeName` в функции [Navigate](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx).  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## Пример  
 В следующем примере показано преобразование из `TypeName` в `Type` и наоборот.  
  
```  
  
// Convert from Type to TypeName TypeName tn = TypeName(MainPage::typeid); // Convert back from TypeName to Type Type^ tx2 = (Type^)(tn);  
  
```  
  
## Эквивалент в .NET Framework  
 .NET Framework программирует `TypeName` проекта как [System.Type](assetId:///System.Type?qualifyHint=False&amp;autoUpgrade=True).  
  
## Требования  
  
## См. также  
 [оператор Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)   
 [Класс Platform::Type](../cppcx/platform-type-class.md)