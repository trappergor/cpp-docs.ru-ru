---
title: HelpContext (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: 8ec13d785ae491a4082d0bbdc908448cb1b8a49c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69490916"
---
# <a name="helpcontext"></a>helpcontext

Указывает идентификатор контекста, позволяющий пользователю просматривать сведения об этом элементе в файле **справки** .

## <a name="syntax"></a>Синтаксис

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>Параметры

*id*<br/>
Идентификатор контекста раздела справки. См [. справку HTML: Контекстно-зависимая справка для](../../mfc/html-help-context-sensitive-help-for-your-programs.md) ваших программ для получения дополнительных сведений об идентификаторах контекста.

## <a name="remarks"></a>Примечания

Атрибут **HelpContext** C++ имеет те же функциональные возможности, что и атрибут MIDL для [HelpContext](/windows/win32/Midl/helpcontext) .

## <a name="example"></a>Пример

Пример использования **HelpContext**см. в примере для [DefaultValue](defaultvalue.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**Interface**, **typedef**, **класс**, метод, свойство|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)