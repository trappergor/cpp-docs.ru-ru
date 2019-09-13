---
title: async_uuid (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.async_uuid
helpviewer_keywords:
- async_uuid attribute
ms.assetid: 235cb0d7-be58-4dd9-983c-e2a21bbc42c6
ms.openlocfilehash: 70e73a6286a4b6adaba20b5a35dc16d8389b1948
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501866"
---
# <a name="async_uuid"></a>async_uuid

Указывает UUID, который направляет компилятор MIDL для определения синхронных и асинхронных версий COM-интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
[async_uuid (uuid)]
```

### <a name="parameters"></a>Параметры

*uuid*<br/>
UUID, определяющий версию интерфейса.

## <a name="remarks"></a>Примечания

Атрибут **async_uuid** C++ имеет те же функциональные возможности, что и атрибут [async_uuid](/windows/win32/Midl/async-uuid) MIDL.

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
|**Относится к**|`interface`|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|**Dual**, **DISP**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)