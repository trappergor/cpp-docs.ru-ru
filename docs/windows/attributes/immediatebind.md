---
title: иммедиатебинд (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.immediatebind
helpviewer_keywords:
- immediatebind attribute
ms.assetid: 186d40e6-9166-4d0c-9853-4e7e4d25226f
ms.openlocfilehash: 8c659f23d6828616c4a48522b61330336e994cbb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514654"
---
# <a name="immediatebind"></a>immediatebind

Указывает, что база данных будет уведомлена сразу обо всех изменениях свойства объекта, привязанного к данным.

## <a name="syntax"></a>Синтаксис

```cpp
[immediatebind]
```

## <a name="remarks"></a>Примечания

Атрибут **иммедиатебинд** C++ имеет те же функциональные возможности, что и атрибут [иммедиатебинд](/windows/win32/Midl/immediatebind) MIDL.

## <a name="example"></a>Пример

Пример использования **иммедиатебинд**см. в разделе [Привязка](bindable.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|Метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[requestedit](requestedit.md)