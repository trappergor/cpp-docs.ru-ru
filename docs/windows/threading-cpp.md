---
title: "threading (C++) | Microsoft Docs"
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
  - "vc-attr.threading"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "threading attribute"
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# threading (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает потоковую модель для com\-объекта.  
  
## Синтаксис  
  
```  
  
      [ threading(  
   model=enumeration  
) ]  
```  
  
#### Параметры  
 ***model*** \(необязательно\)  
 Потоковых одну из следующих моделей.  
  
-   **плоский** потоковая модель Подразделение \(\)  
  
-   **нейтрально** \(компоненты платформы .NET Framework без пользовательского интерфейса\)  
  
-   **Одинарный** \(простой работа с потоками\)  
  
-   **free** работа с потоками \(free\)  
  
-   **оба** \(threading подразделения и свободена\)  
  
 Значение по умолчанию **плоский**.  
  
## Заметки  
 **Потоки** Атрибут C\+\+ не отображается в созданный файл idl, но будет использоваться в реализации com\-объекта.  
  
 В проектах библиотеки ATL, если [CoClass](../windows/coclass.md) атрибут также присутствуют, потоковая модель, определенная by модель передает в качестве параметра шаблона  [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) класс, вставленный  **CoClass** атрибут.  
  
 **Потоки** атрибута к условий также  [event\_source](../windows/event-source.md).  
  
## Пример  
 См. [лицензировано](../windows/licensed.md) пример использования образца  **Потоки**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**"  `struct`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|**CoClass**|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [COM Attributes](../Topic/COM%20Attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Поддержка многопоточности для устаревшего кода \(Visual C\+\+\)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [Neutral Apartments](http://msdn.microsoft.com/library/windows/desktop/ms681813)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)