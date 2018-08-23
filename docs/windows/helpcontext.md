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
ms.openlocfilehash: 8d782246f44148805f9acc8d912b0fbf554227f7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595732"
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

*id*  
Идентификатор контекста справки. См. в разделе [HTML-справки: Context-Sensitive для ваших программ](../mfc/html-help-context-sensitive-help-for-your-programs.md) Дополнительные сведения о контексте идентификаторы.

## <a name="remarks"></a>Примечания

**Helpcontext** атрибут C++ имеет ту же функциональность, что [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) описании атрибута MIDL.

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

[Атрибуты IDL](../windows/idl-attributes.md)  
[Атрибуты интерфейса](../windows/interface-attributes.md)  
[Атрибуты классов](../windows/class-attributes.md)  
[Атрибуты метода](../windows/method-attributes.md)  
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)  
[helpfile](../windows/helpfile.md)  
[helpstring](../windows/helpstring.md)  