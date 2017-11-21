---
title: "строка (C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.string
dev_langs: C++
helpviewer_keywords: string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0293785b9552b2e5696b9334e81aebf44c3bc4b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="string-c"></a>string (C++)
Указывает, что одномерный массив `char`, `wchar_t`, **байтов** (или эквивалентную) массив или указатель на такой массив должен рассматриваться как строка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[string]  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Строка** языка C++ имеет ту же функциональность, что [строка](http://msdn.microsoft.com/library/windows/desktop/aa367270) языка MIDL.  
  
## <a name="example"></a>Пример  
 Следующий код показывает, как использовать **строки** в интерфейсе и на typedef:  
  
```  
// cpp_attr_ref_string.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export, string] typedef char a[21];  
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   [id(1)] HRESULT Method3([in, string] char *pC);  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Массив или указатель на массив, параметр интерфейса, метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты массивов](../windows/array-attributes.md)   
 [export](../windows/export.md)   
