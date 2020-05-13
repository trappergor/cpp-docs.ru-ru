---
title: HelpContext (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: 292db21e8092284a92b09ef3f889bb0475d0d886
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167008"
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
|**Применение**|**Interface**, **typedef**, **класс**, метод, свойство|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)
