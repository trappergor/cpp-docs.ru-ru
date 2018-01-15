---
title: "RDX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.rdx
dev_langs: C++
helpviewer_keywords: rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d656af60ec14309227fc73d81bd0f14638637d48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
