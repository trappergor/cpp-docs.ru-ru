---
title: RDX | Документация Майкрософт
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
ms.openlocfilehash: 423cd4585fa6e9ae5a5fbb16cf7d5c43aaf7c152
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605931"
---
# <a name="rdx"></a>rdx

Создает раздел реестра или изменяет существующий раздел реестра.

## <a name="syntax"></a>Синтаксис

```cpp
[ rdx(
   key,
   valuename=NULL,
   regtype
) ]
```

### <a name="parameters"></a>Параметры

*key*  
Имя ключа, который требуется создать или открыть.

*valueName* (необязательно)  
Задает поле значение, устанавливаемое значение. Если значение поля с таким именем еще не существует в ключе, он добавляется.

*regtype*  
Тип добавляемого раздела реестра. Может принимать одно из следующих: `text`, `dword`, `binary`, или `CString`.

## <a name="remarks"></a>Примечания

**Rdx** атрибут C++ создает или изменяет существующий раздел реестра для COM-компонента. Атрибут добавляет макрос BEGIN_RDX_MAP объект, реализующий целевой элемент. `RegistryDataExchange`, внедрены в результате макрос BEGIN_RDX_MAP, функция может использоваться для передачи данных между реестра и элементов данных

Этот атрибут может использоваться в сочетании с [coclass](../windows/coclass.md), [progid](../windows/progid.md), или [vi_progid](../windows/vi-progid.md) атрибутов или другие атрибуты, которые подразумевает один из них.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс** или **структуры** член|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="example"></a>Пример

Следующий код добавляет ключ реестра с именем MyValue в системе, описывающее CMyClass COM-компонента.

```cpp
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