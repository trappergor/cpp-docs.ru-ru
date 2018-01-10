---
title: "v1_enum | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.v1_enum
dev_langs: C++
helpviewer_keywords: v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6475f49653a38cd759b99379c3a9e56178364fdc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="v1enum"></a>v1_enum
Направляет передачи заданного перечислимого типа как сущность 32 бита, а не 16-разрядное значение по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[v1_enum]  
  
```  
  
## <a name="remarks"></a>Примечания  
 **V1_enum** языка C++ имеет ту же функциональность, что [v1_enum](http://msdn.microsoft.com/library/windows/desktop/aa367303) языка MIDL.  
  
## <a name="example"></a>Пример  
 В следующем коде показано использование **v1_enum**:  
  
```  
// cpp_attr_ref_v1_enum.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export, v1_enum]   
enum eList {   
   e1 = 1,   
   e2 = 2  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Перечислимый тип|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)   
