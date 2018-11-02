---
title: в поле (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.in
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
ms.openlocfilehash: bf23b1c776eccc284e5329b62bd45b0bd678823f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449703"
---
# <a name="in-c"></a>in (C++)

Указывает, что параметр передается из вызывающей процедуры вызываемой процедуры.

## <a name="syntax"></a>Синтаксис

```cpp
[in]
```

## <a name="remarks"></a>Примечания

**В** атрибут C++ имеет ту же функциональность, что [в](/windows/desktop/Midl/in) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в разделе [bindable](bindable.md) пример демонстрирует использование **в**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса, метод интерфейса|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|**retval**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[id](id.md)<br/>
[out](out-cpp.md)