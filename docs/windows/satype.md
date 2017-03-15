---
title: "satype | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.satype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "satype attribute"
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# satype
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает тип данных SAFEARRAY структура.  
  
## Синтаксис  
  
```  
  
      [ satype(  
   data_type  
) ]  
```  
  
#### Параметры  
 *data\_type*  
 Тип данных SAFEARRAY структура данных, которая передается в качестве параметра методу интерфейса.  
  
## Требования  
  
### Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Параметр интерфейса, метод интерфейса|  
|**Repeatable**|Нет|  
|**Обязательные атрибуты**|None|  
|**Недопустимые атрибуты**|None|  
  
## Заметки  
 **satype** атрибут C\+\+ определяет тип данных   **SAFEARRAY**.  
  
> [!NOTE]
>  Уровень косвенного обращения удален из SAFEARRAY указатель в созданном файле idl от того, как она объявлена в cpp\-файле.  
  
## Пример  
  
```  
// cpp_attr_ref_satype.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyModule")];  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A {  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## См. также  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [id](../windows/id.md)   
 [Attributes Samples](http://msdn.microsoft.com/ru-ru/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)