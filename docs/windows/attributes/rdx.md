---
title: RDX (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: ffee10ea334c6c425aa5ecd81705ef1915dc80c0
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791227"
---
# <a name="rdx"></a>rdx

Создает раздел реестра или изменяет существующий раздел реестра.

## <a name="syntax"></a>Синтаксис

```cpp
[ rdx(key, valuename=NULL, regtype) ]
```

### <a name="parameters"></a>Параметры

*key*<br/>
Имя ключа, который требуется создать или открыть.

*valueName*<br/>
(Необязательно) Задает поле значение, устанавливаемое значение. Если значение поля с таким именем еще не существует в ключе, он добавляется.

*regtype*<br/>
Тип добавляемого раздела реестра. Может принимать одно из следующих: `text`, `dword`, `binary`, или `CString`.

## <a name="remarks"></a>Примечания

**Rdx** атрибут C++ создает или изменяет существующий раздел реестра для COM-компонента. Атрибут добавляет макрос BEGIN_RDX_MAP объект, реализующий целевой элемент. `RegistryDataExchange`, внедрены в результате макрос BEGIN_RDX_MAP, функция может использоваться для передачи данных между реестра и элементов данных

Этот атрибут может использоваться в сочетании с [coclass](coclass.md), [progid](progid.md), или [vi_progid](vi-progid.md) атрибутов или другие атрибуты, которые подразумевает один из них.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс** или **структуры** член|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

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

[Атрибуты COM](com-attributes.md)<br/>
[registration_script](registration-script.md)  