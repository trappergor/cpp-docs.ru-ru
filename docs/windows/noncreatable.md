---
title: "noncreatable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.noncreatable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "noncreatable attribute"
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# noncreatable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет объект, который не может быть создан самостоятельно.  
  
## Синтаксис  
  
```  
  
[noncreatable]  
  
```  
  
## Заметки  
 **noncreatable** Атрибут C\+\+ имеет ту же функциональность, что и  [noncreatable](http://msdn.microsoft.com/library/windows/desktop/aa367118) Атрибут MIDL и автоматически передается в idl\-файл генерируемый компилятором.  
  
 Когда этот атрибут используется в рамках проекта, использующий библиотеку ATL, расширения функциональности атрибута изменяется.  В дополнение к приведенной выше расширений функциональности также вставляет атрибут OBJECT\_ENTRY\_NON\_CREATEABLE\_EX\_AUTO макрос.  Этот макрос указывает на библиотеку ATL, что объект не может быть создан ней.  
  
## Пример  
  
```  
// cpp_attr_ref_noncreatable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("11111111-1111-1111-1111-111111111111")]  
__interface A   
{  
};  
  
[coclass, uuid("11111111-1111-1111-1111-111111111112"), noncreatable]  
class CMyClass : public A   
{  
   HRESULT xx();  
};  
```  
  
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
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)