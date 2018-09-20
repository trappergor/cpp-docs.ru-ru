---
title: HelpContext | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpcontext
dev_langs:
- C++
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d9c2efecf34e5d58f633bc21e62801157b1b8955
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388593"
---
# <a name="helpcontext"></a>helpcontext

Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в **помочь** файл.

## <a name="syntax"></a>Синтаксис

```cpp
[ helpcontext(
   id
) ]
```

### <a name="parameters"></a>Параметры

*id*<br/>
Идентификатор контекста справки. См. в разделе [HTML-справки: Context-Sensitive для ваших программ](../mfc/html-help-context-sensitive-help-for-your-programs.md) Дополнительные сведения о контексте идентификаторы.

## <a name="remarks"></a>Примечания

**Helpcontext** атрибут C++ имеет ту же функциональность, что [helpcontext](/windows/desktop/Midl/helpcontext) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [defaultvalue](../windows/defaultvalue.md) пример демонстрирует использование **helpcontext**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**интерфейс**, **typedef**, **класс**, метод, свойство|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты интерфейса](../windows/interface-attributes.md)<br/>
[Атрибуты классов](../windows/class-attributes.md)<br/>
[Атрибуты метода](../windows/method-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](../windows/helpfile.md)<br/>
[helpstring](../windows/helpstring.md)  