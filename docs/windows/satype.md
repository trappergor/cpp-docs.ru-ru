---
title: satype | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.satype
dev_langs:
- C++
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a5376e0e830654c15dc31522b07ed53af4492bf
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603398"
---
# <a name="satype"></a>satype
Указывает тип данных `SAFEARRAY` структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ satype(  
   data_type  
) ]  
```  
  
### <a name="parameters"></a>Параметры  
 *data_type*  
 Тип данных для `SAFEARRAY` структура данных, которая передается как параметр метода интерфейса.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|Параметр интерфейса, метод интерфейса|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
## <a name="remarks"></a>Примечания  
 **Satype** C++ атрибут указывает тип данных `SAFEARRAY`.  
  
> [!NOTE]
>  Уровень косвенности удаляется из `SAFEARRAY` указатель на созданного IDL-файла из как объявлено в CPP-файл.  
  
## <a name="example"></a>Пример  
  
```cpp  
// cpp_attr_ref_satype.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyModule")];  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A {  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Атрибуты компилятора](../windows/compiler-attributes.md)   
 [Атрибуты параметра](../windows/parameter-attributes.md)   
 [Атрибуты метода](../windows/method-attributes.md)   
 [id](../windows/id.md)   