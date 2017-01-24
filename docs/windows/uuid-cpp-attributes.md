---
title: "uuid (C++ Attributes) | Microsoft Docs"
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
  - "vc-attr.uuid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uuid attribute"
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# uuid (C++ Attributes)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает уникальный идентификатор класса или интерфейса.  
  
## Синтаксис  
  
```  
  
      [ uuid(  
   "uuid"  
) ]  
```  
  
#### Параметры  
 *uuid*  
 128 Бит, уникального идентификатора.  
  
## Заметки  
 Если определение интерфейса или класса не определен `uuid` Атрибут C\+\+, затем компилятор Visual C\+\+ предоставляет одно.  При указании a `uuid`необходимо включить кавычки.  
  
 Если не указано `uuid`после этого компилятор создает один и тот же идентификатор GUID для интерфейсов и классов с тем же именем в различных проектах атрибута на компьютере.  
  
 Uuidgen.exe или Guidgen.exe можно использовать, чтобы создавать собственные уникальные идентификаторы.  \(Выполняться одно из этих средств, нажмите кнопку **Запуск** и щелкните элемент  **Выполнить** в меню.  Введите имя требуемого tools\).  
  
 При использовании в проекте, который также не использует библиотеки ATL, указав `uuid` атрибут аналогичен определение  [UUID](../cpp/uuid-cpp.md) модификатор \_\_declspec.  Восстановление `uuid` класса можно использовать  [\_\_uuidof](../cpp/uuidof-operator.md)  
  
## Пример  
 См. [bindable](../windows/bindable.md) пример использования образца  `uuid`.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**"  `struct`"  `interface`"  **union**"  `enum`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [uuid](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)