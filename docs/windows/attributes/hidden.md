---
title: Hidden (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.hidden
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
ms.openlocfilehash: e0e3c5cb0355f3bedd8ecee57b034f0d9dde87df
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224439"
---
# <a name="hidden"></a>hidden

Указывает, что элемент существует, но не должен отображаться в браузере, ориентированном на пользователя.

## <a name="syntax"></a>Синтаксис

```cpp
[hidden]
```

## <a name="remarks"></a>Remarks

Атрибут **Hidden** C++ имеет те же функциональные возможности, что и [скрытый](/windows/win32/Midl/hidden) атрибут MIDL.

## <a name="example"></a>Пример

См. пример для [привязки](bindable.md) к примеру, как использовать **скрытый**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**интерфейс**, **`class`** , **`struct`** , метод, свойство|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|**coclass** (при применении к **`class`** или **`struct`** )|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также статью

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)
