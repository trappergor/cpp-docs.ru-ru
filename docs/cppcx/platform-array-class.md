---
title: "Platform::Array - класс | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::Array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Array - класс"
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Array - класс
Представляет изменяемый одномерный массив, который можно получать и передавать через двоичный интерфейс приложений \(ABI\).  
  
## Синтаксис  
  
```cpp  
  
template <typename T>  
    private ref class Array<TArg,1> :   
         public WriteOnlyArray<TArg, 1>,  
         public IBoxArray<TArg>  
  
```  
  
## Участники  
 Platform::Array наследует все методы из [Класс Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) и реализует свойство `Value`[Интерфейс Platform::IBoxArray](../cppcx/platform-iboxarray-interface.md).  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструкторы массивов](../cppcx/array-constructors.md)|Инициализирует одномерный изменяемый массив типов, указанных в параметре шаблона класса *T*.|  
  
### Методы  
 См. раздел [Класс Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md).  
  
### Свойства  
  
|||  
|-|-|  
|[Свойство Array::Value](../cppcx/array-value-property.md)|Получает дескриптор текущего массива.|  
  
## Заметки  
 Класс Array является запечатанным и наследовать его нельзя.  
  
 Система типов среды выполнения Windows не поддерживает концепцию массивов массивов и, таким образом, невозможно передать IVector\<Platform::Array\<T\>\> в качестве возвращаемого значения или параметра метода. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.  
  
 Дополнительные сведения о том, когда и как можно использовать Platform::Array, см. в разделе [Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
 Система типов среды выполнения Windows не поддерживает концепцию массивов массивов и, таким образом, невозможно передать IVector\<Platform::Array\<T\>\> в качестве возвращаемого значения или параметра метода. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.  
  
 Этот класс определен в заголовке vccorlib.h, который автоматически включается компилятором. Он отображается в Intellisense, но не в обозревателе объектов, поскольку нет открытого типа, определенного в platform.winmd.  
  
## Требования  
 Параметр компилятора: **\/ZW**  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)   
 [Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)