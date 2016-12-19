---
title: "export | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.export"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "export attribute"
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# export
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Структура данных будет располагаться в idl\-файле.  
  
## Синтаксис  
  
```  
  
[export]  
  
```  
  
## Заметки  
 **Экспорт** Атрибут C\+\+ будет структуру данных располагаться в idl\-файле, а затем быть доступен в библиотеке типов в формате binary\-совместимого, который делает его доступным для использования с любым языком.  
  
 Нельзя применить **Экспорт** атрибут к классу, даже если класс имеет только открытые члены \(количество a  `struct`\).  
  
 При экспорте безымянное `enum`s или  `struct`s, они будут заданными именами, начинающиеся с символа  **\_\_unnamed**x, где x последовательный номер.  
  
 Определения типов допустимые для экспорта базовые типы, структуры, объединения, перечисления или идентификаторы типа.  См. [typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) для получения дополнительных сведений.  
  
## Пример  
 В следующем примере кода демонстрируется применение **Экспорт** атрибут:  
  
```  
// cpp_attr_ref_export.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**union**"  `typedef`"  `enum`"  `struct`или  `interface`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)