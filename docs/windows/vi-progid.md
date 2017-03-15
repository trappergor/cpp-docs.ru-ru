---
title: "vi_progid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.vi_progid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vi_progid attribute"
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# vi_progid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет версия\-независимую форму программного идентификатора.  
  
## Синтаксис  
  
```  
  
      [ vi_progid(  
   name  
) ];  
```  
  
#### Параметры  
 *name*  
 Является независимым от версии идентификатор progid, представляющее объект.  
  
 Имеется Progid удобную для восприятия версия идентификатора класса \(CLSID\), используемого для идентификации объектов COM И ActiveX.  
  
## Заметки  
 **vi\_progid** Атрибут C\+\+ позволяет указать является независимым от версии идентификатор progid для com\-объекта.  Идентификатор progid имеет форму *Имя1*.*имя2*.*версия*.  Является независимым от версии идентификатор progid не имеет a *версия*.  Можно указать оба **идентификатор progid** и  **vi\_progid** атрибуты компонентного класса.  Если не указано **vi\_progid**, является независимым от версии идентификатор progid \- значение, заданное  [идентификатор progid](../Topic/progid.md) атрибут.  
  
 **vi\_progid** неявно  **CoClass** атрибут, т е при указании  **vi\_progid**та же, что и определение  **CoClass** и  **vi\_progid** атрибуты.  
  
 Vi\_progid атрибут вызывает класс автоматически был зарегистрирован с указанным именем.  Созданный файл idl не отображают значение программного идентификатора.  
  
 В проектах библиотеки ATL, если [CoClass](../windows/coclass.md) атрибут также присутствуют, указанный идентификатор progid используется  **GetVersionIndependentProgID** \(появилась функция  **CoClass** атрибут\).  
  
## Пример  
 См. [CoClass](../windows/coclass.md) пример использования образца  **vi\_progid**.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**класс**"  `struct`|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
 Дополнительные сведения о контекстах атрибута см. в разделе [Контексты атрибута](../windows/attribute-contexts.md).  
  
## См. также  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [ProgID Key](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)