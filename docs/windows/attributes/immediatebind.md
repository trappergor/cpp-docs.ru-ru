---
title: иммедиатебинд (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.immediatebind
helpviewer_keywords:
- immediatebind attribute
ms.assetid: 186d40e6-9166-4d0c-9853-4e7e4d25226f
ms.openlocfilehash: d0fb85a3f5642bc5fffcad29892ca15bb13a1ce0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166918"
---
# <a name="immediatebind"></a>immediatebind

Указывает, что база данных будет уведомлена сразу обо всех изменениях свойства объекта, привязанного к данным.

## <a name="syntax"></a>Синтаксис

```cpp
[immediatebind]
```

## <a name="remarks"></a>Remarks

Атрибут **иммедиатебинд** C++ имеет те же функциональные возможности, что и атрибут [иммедиатебинд](/windows/win32/Midl/immediatebind) MIDL.

## <a name="example"></a>Пример

Пример использования **иммедиатебинд**см. в разделе [Привязка](bindable.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[requestedit](requestedit.md)
