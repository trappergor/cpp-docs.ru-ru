---
title: async_uuid (C++ атрибут COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.async_uuid
helpviewer_keywords:
- async_uuid attribute
ms.assetid: 235cb0d7-be58-4dd9-983c-e2a21bbc42c6
ms.openlocfilehash: 4c2bca9165d8b23f8cfa4f0f5523c882fd2f52bf
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035800"
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

**Async_uuid** C++ атрибут имеет ту же функциональность, что [async_uuid](/windows/desktop/Midl/async-uuid) описании атрибута MIDL.

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