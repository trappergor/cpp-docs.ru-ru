---
title: registration_script (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.registration_script
dev_langs:
- C++
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: edc9d5aa1d7c49de34ee3dbb02d2a55542962a50
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792413"
---
# <a name="registrationscript"></a>registration_script

Выполняет указанную регистрацию пользовательский скрипт.

## <a name="syntax"></a>Синтаксис

```cpp
[ registration_script(script) ]
```

### <a name="parameters"></a>Параметры

*сценарий*<br/>
Полный путь к файлу сценария (.rgs) регистрации. Значение **none**, такие как `script = "none"`, означает, что компонентный класс не требования для регистрации.

## <a name="remarks"></a>Примечания

**Registration_script** атрибут C++ выполняет скрипт регистрации, определяемое *скрипт*. Если этот атрибут не указан, используется стандартный RGS-файл, (содержащий сведения о регистрации компонента). Дополнительные сведения о файлах .rgs, см. в разделе [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).

Этот атрибут требует, чтобы [coclass](coclass.md), [progid](progid.md), или [vi_progid](vi-progid.md) (или другой атрибут, который подразумевает один из них) также применялся к этому элементу.

## <a name="example"></a>Пример

Следующий код указывает, что компонент имеет сценарий реестра с именем cpp_attr_ref_registration_script.rgs.

```cpp
// cpp_attr_ref_registration_script.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="REG")];

[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]
__interface IFace {};

// requires "cpp_attr_ref_registration_script.rgs"
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]
class CMyClass:public IFace {};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Один или несколько из следующих: `coclass`, `progid`, или `vi_progid`.|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты COM](com-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[rdx](rdx.md)  