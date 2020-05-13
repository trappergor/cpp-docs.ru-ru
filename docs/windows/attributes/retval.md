---
title: retval (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.retval
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
ms.openlocfilehash: 5aded4588614eb4171e31a588f125ea8aa8de7ee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166345"
---
# <a name="retval"></a>retval

Определяет параметр, который получает возвращаемое значение элемента.

## <a name="syntax"></a>Синтаксис

```cpp
[retval]
```

## <a name="remarks"></a>Remarks

Атрибут **retval** C++ имеет те же функциональные возможности, что и атрибут [retval](/windows/win32/Midl/retval) в формате MIDL.

значение **retval** должно присутствовать в последнем аргументе в объявлении функции.

## <a name="example"></a>Пример

См. пример для [привязки](bindable.md) к примеру использования параметра **retval**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса, метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|**out**|
|**Недопустимые атрибуты**|**В поле**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)
