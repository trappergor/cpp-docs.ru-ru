---
title: retval (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.retval
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
ms.openlocfilehash: 9f5ad86a289f8904278a58636e66809ae0edd55b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035103"
---
# <a name="retval"></a>retval

Назначает параметр, который получает возвращаемое значение члена.

## <a name="syntax"></a>Синтаксис

```cpp
[retval]
```

## <a name="remarks"></a>Примечания

**Retval** атрибут C++ имеет ту же функциональность, что [retval](/windows/desktop/Midl/retval) описании атрибута MIDL.

**retval** должны располагаться на последний аргумент в объявлении функции.

## <a name="example"></a>Пример

См. в примере [bindable](bindable.md) использовать образец **retval**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|**out**|
|**Недопустимые атрибуты**|**in**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)