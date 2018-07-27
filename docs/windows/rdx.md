---
title: RDX | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.rdx
dev_langs:
- C++
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7647ca56e3159564826efa9caf438456b9ae3568
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878961"
---
# <a name="rdx"></a>rdx
Создает раздел реестра или изменяет существующий раздел реестра.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ rdx(   
   key,   
   valuename=NULL,   
   regtype   
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 `key`  
 Имя ключа для создания или открытия.  
  
 `valuename` (необязательно)  
 Указывает задаваемое полем значения. Если значение поля с таким именем уже существует в ключе, он добавляется.  
  
 *regtype*  
 Тип добавляемого раздела реестра. Может принимать одно из следующих действий: **текст**, **dword**, **двоичных**, или `CString`.  
  
## <a name="remarks"></a>Примечания  
 **Rdx** атрибута C++ создает или изменяет существующий раздел реестра для COM-компонента. Атрибут добавляет макрос BEGIN_RDX_MAP объект, реализующий целевой элемент. `RegistryDataExchange`, функция, введенный в результате макрос BEGIN_RDX_MAP может использоваться для передачи данных между реестром и члены данных  
  
 Этот атрибут можно использовать в сочетании с [coclass](../windows/coclass.md), [progid](../windows/progid.md), или [vi_progid](../windows/vi-progid.md) атрибутов или другие атрибуты, которые означает одно из следующих.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**Класс** или `struct` члена|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="example"></a>Пример  
 Следующий код добавляет ключ реестра с именем MyValue в системе, описывающий CMyClass COM-компонента.  
  
```  
// cpp_attr_ref_rdx.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
  
[module (name="MyLib")];  
  
class CMyClass {  
public:  
   CMyClass() {  
      strcpy_s(m_sz, "SomeValue");  
   }  
  
   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]   
   char m_sz[256];  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Атрибуты COM](../windows/com-attributes.md)   
 [registration_script](../windows/registration-script.md)   
