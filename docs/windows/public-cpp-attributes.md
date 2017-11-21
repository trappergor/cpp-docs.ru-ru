---
title: "Public (атрибуты C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.public
dev_langs: C++
helpviewer_keywords: public attribute
ms.assetid: c42e1fd5-6cb1-48fe-8a03-95f2a2e0137c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c464f2fe2261018f2f18282b3cf3c2a62f31fde4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="public-c-attributes"></a>public (атрибуты C++)
Гарантирует, что typedef перейдет в библиотеке типов, даже если нет ссылок из в IDL-файл.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
[public]  
  
```  
  
## <a name="remarks"></a>Примечания  
 **Открытый** языка C++ имеет ту же функциональность, что [открытый](http://msdn.microsoft.com/library/windows/desktop/aa367150) языка MIDL.  
  
## <a name="example"></a>Пример  
 Следующий код показывает, как использовать **открытый** атрибута:  
  
```  
// cpp_attr_ref_public.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export, public] typedef long MEMBERID;  
  
[dispinterface, uuid(99999999-9999-9999-9999-000000000000)]  
__interface IFireTabCtrl : IDispatch  
{  
   [id(2)] long procedure ([in, optional] VARIANT i);  
};  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|`typedef`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)   
