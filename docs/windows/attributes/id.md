---
title: идентификатор (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.id
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
ms.openlocfilehash: b7bcbd9229529ec00a3b778cafd5678d47af950c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630051"
---
# <a name="id"></a>id

Указывает *dispid* параметра для функции-члена (свойство или метод, в интерфейс или диспетчерский интерфейс).

## <a name="syntax"></a>Синтаксис

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>Параметры

*Идентификатор DISPID*<br/>
Идентификатор диспетчеризации метода интерфейса.

## <a name="remarks"></a>Примечания

**Идентификатор** атрибут C++ имеет ту же функциональность, что [идентификатор](/windows/desktop/Midl/id) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [bindable](bindable.md) пример демонстрирует использование **идентификатор**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты элементов данных](data-member-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[in](in-cpp.md)<br/>
[out](out-cpp.md)