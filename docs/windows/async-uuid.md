---
title: async_uuid | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.async_uuid
dev_langs:
- C++
helpviewer_keywords:
- async_uuid attribute
ms.assetid: 235cb0d7-be58-4dd9-983c-e2a21bbc42c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 029528baabcc32c14fb6b35e4a13f4118602d5d5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417804"
---
# <a name="asyncuuid"></a>async_uuid

Указывает UUID, компилятор MIDL определить синхронные и асинхронные версии COM-интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
[async_uuid (
   uuid
)]
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

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты интерфейса](../windows/interface-attributes.md)  