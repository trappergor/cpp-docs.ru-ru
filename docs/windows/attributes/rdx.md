---
title: RDX (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.rdx
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
ms.openlocfilehash: 2790c3de01d21242daee73fc442ad22d88739355
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023884"
---
# <a name="rdx"></a>rdx

Создает раздел реестра или изменяет существующий раздел реестра.

## <a name="syntax"></a>Синтаксис

```cpp
[ rdx(key, valuename=NULL, regtype) ]
```

### <a name="parameters"></a>Параметры

*клавиша*<br/>
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

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

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