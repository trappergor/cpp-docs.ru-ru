---
title: async_uuid (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.async_uuid
helpviewer_keywords:
- async_uuid attribute
ms.assetid: 235cb0d7-be58-4dd9-983c-e2a21bbc42c6
ms.openlocfilehash: 559500a1390e0d1bac8344d0ffcfc1bdd9ad55f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490913"
---
# <a name="asyncuuid"></a>async_uuid

Указывает UUID, компилятор MIDL определить синхронные и асинхронные версии COM-интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
[async_uuid (uuid)]
```

### <a name="parameters"></a>Параметры

*uuid*<br/>
UUID, которое определяет версию интерфейса.

## <a name="remarks"></a>Примечания

**Async_uuid** атрибут C++ имеет ту же функциональность, что [async_uuid](/windows/desktop/Midl/async-uuid) описании атрибута MIDL.

## <a name="example"></a>Пример

```cpp
// cpp_attr_ref_async_uuid.cpp
// compile with: /LD
#include <Windows.h>
[module(name="Test")];
[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb"),
async_uuid("e8583106-38fd-487e-912e-4fc8645c677e")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|`interface`|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|**двойной**, **disp-интерфейс**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)