---
title: ID (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.id
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
ms.openlocfilehash: 6f1d1d2b9d147e8b33b3b5fae629e0805971bb71
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501410"
---
# <a name="id"></a>id

Задает параметр *DISPID* для функции-члена (свойства или метода в интерфейсе или DISP).

## <a name="syntax"></a>Синтаксис

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>Параметры

*DISPID*<br/>
Идентификатор диспетчеризации для метода интерфейса.

## <a name="remarks"></a>Примечания

Атрибут **ID** C++ имеет те же функциональные возможности, что и атрибут [ID](/windows/win32/Midl/id) MIDL.

## <a name="example"></a>Пример

Пример использования **идентификатора**см. в примере для [привязки](bindable.md) .

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
[Атрибуты элементов данных](data-member-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[in](in-cpp.md)<br/>
[out](out-cpp.md)