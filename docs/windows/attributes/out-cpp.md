---
title: out (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.out
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
ms.openlocfilehash: 6ab8fdf691e2220087f5c5d64bb70c5deb27675c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214701"
---
# <a name="out-c"></a>out (C++)

Определяет параметры-указатели, которые возвращаются из вызываемой процедуры в вызывающую (от сервера к клиенту).

## <a name="syntax"></a>Синтаксис

```cpp
[out]
```

## <a name="remarks"></a>Remarks

Атрибут **out** языка C++ имеет ту же функциональность, как и атрибут [out](/windows/win32/Midl/out-idl) языка MIDL.

## <a name="example"></a>Пример

Просмотрите пример с [bindable](bindable.md) , чтобы увидеть, как можно использовать **out**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Параметр интерфейса|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты параметра](parameter-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[идентификатор](id.md)
