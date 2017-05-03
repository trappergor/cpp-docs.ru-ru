---
title: "Класс Platform::Type | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс Platform::Type"
ms.assetid: d6b03f1e-b240-49b9-a08e-53a460030475
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Класс Platform::Type
Содержит сведения среды выполнения о типе — в частности, имя строки и код типа. Получается вызовом метода [Object::GetType](../cppcx/object-gettype-method.md) в любом объекте или использованием оператора [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) в имени класса или структуры.  
  
## Синтаксис  
  
```cpp  
public ref class Platform::Type :      Platform::Object,      Platform::Details::IEquatable,      Platform::Details::IPrintable  
```  
  
## Заметки  
 Класс `Type` удобен в приложениях, где должна выполняться непосредственная обработка с использованием оператора `if` или `switch`, образующего ветви на основе типа объекта времени выполнения. Код типа, описывающий категорию типа, извлекается с помощью функции\-члена [Метод Type::GetTypeCode](../cppcx/type-gettypecode-method.md).  
  
## Открытые методы  
  
|||  
|-|-|  
|[Метод Type::GetTypeCode](../cppcx/type-gettypecode-method.md)|Возвращает значение [Перечисление Platform::TypeCode](../cppcx/platform-typecode-enumeration.md) для объекта.|  
  
## Открытые свойства  
  
|||  
|-|-|  
|[Свойство Type::FullName](../cppcx/type-fullname-property.md)|Возвращает [Класс Platform::String](../cppcx/platform-string-class.md)^, который представляет полное имя типа и использует . \(точку\), а не :: \(двойное двоеточие\) в качестве разделителя, например MyNamespace.MyClass.|  
  
## Операторы преобразования  
  
|||  
|-|-|  
|[оператор Type^](../cppcx/operator-subtracttype-hat.md)|Обеспечивает преобразование `Windows::UI::Xaml::Interop::TypeName` в `Platform::Type`.|  
|[оператор Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-subtractwindows-ui-xaml-interop-typename.md)|Обеспечивает преобразование `Platform::Type` в `Windows::UI::Xaml::Interop::TypeName`.|  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)