---
title: "Метод Object::GetType | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::GetType"
ms.assetid: f633d71a-ff80-49f9-931d-189c00b1f6c5
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Object::GetType
Возвращает объект [Platform::Type](../cppcx/platform-type-class.md), который описывает тип среды выполнения объекта.  
  
## Синтаксис  
  
```vb  
Object::GetType()  
```  
  
```csharp  
  
```  
  
## Значение свойства, возвращаемое значение  
 Объект [Platform::Type](../cppcx/platform-type-class.md), который описывает тип среды выполнения объекта.  
  
## Заметки  
 Статическое свойство [Type::GetTypeCode \- метод](../cppcx/type-gettypecode-method.md) можно использовать для получения значения [Перечисление Platform::TypeCode](../cppcx/platform-typecode-enumeration.md), которое представляет текущий тип. Это наиболее полезно для встроенных типов. Код типа для любого класса ссылок помимо [Platform::String](../cppcx/platform-string-class.md) — объект \(1\).  
  
 Класс [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) используется в API Windows как независимый от языка способ передачи сведений о типе между компонентами и приложениями Windows.[Класс Platform::Type](../cppcx/platform-type-class.md) содержит операторы для преобразования `Type` в `TypeName` и наоборот.  
  
 Используйте оператор [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md), чтобы вернуть объект `Platform::Type` для имени класса, например при переходе между страницами XAML.  
  
```  
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);  
```  
  
## См. также  
 [Класс Platform::Type](../cppcx/platform-type-class.md)   
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)   
 [Система типов](../cppcx/type-system-c-cx.md)