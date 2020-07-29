---
title: HelpContext (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: 77c085f96e778b19886c4e6e3c8f07b43fbe8f2c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211987"
---
# <a name="helpcontext"></a>helpcontext

Указывает идентификатор контекста, позволяющий пользователю просматривать сведения об этом элементе в файле **справки** .

## <a name="syntax"></a>Синтаксис

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>Параметры

*идентификатор*<br/>
Идентификатор контекста раздела справки. Дополнительные сведения об идентификаторах контекста см. в разделе [HTML Help: контекстно-зависимая справка для ваших программ](../../mfc/html-help-context-sensitive-help-for-your-programs.md) .

## <a name="remarks"></a>Remarks

Атрибут **HelpContext** C++ имеет те же функциональные возможности, что и атрибут MIDL для [HelpContext](/windows/win32/Midl/helpcontext) .

## <a name="example"></a>Пример

Пример использования **HelpContext**см. в примере для [DefaultValue](defaultvalue.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**интерфейс**, **`typedef`** , **`class`** , метод, свойство|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты класса](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты typedef, enum, Union и struct](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)
