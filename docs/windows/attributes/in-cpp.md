---
title: In (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.in
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
ms.openlocfilehash: f25f15148621d7092858577825dbdd6caa1ae0be
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166800"
---
# <a name="in-c"></a>in (C++)

Указывает, что параметр передается из вызывающей процедуры в вызываемую процедуру.

## <a name="syntax"></a>Синтаксис

```cpp
[in]
```

## <a name="remarks"></a>Remarks

Атрибут **in** C++ имеет те же функциональные возможности, что и [в](/windows/win32/Midl/in) атрибуте MIDL.

## <a name="example"></a>Пример

Пример использования в см. **в**разделе о возможности [привязки](bindable.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса, метод интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|**retval**|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[идентификатор](id.md)<br/>
[out](out-cpp.md)
