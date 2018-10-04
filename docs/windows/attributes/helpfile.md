---
title: HelpFile (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpfile
dev_langs:
- C++
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9a498cefce01d5a22df5211d0f7bb2f64e3a7b79
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792553"
---
# <a name="helpfile"></a>helpfile

Задает имя файла справки для библиотеки типов.

## <a name="syntax"></a>Синтаксис

```cpp
[ helpfile("filename") ]
```

### <a name="parameters"></a>Параметры

*filename*<br/>
Имя файла, который содержит разделы справки.

## <a name="remarks"></a>Примечания

**Helpfile** атрибут C++ имеет ту же функциональность, что [helpfile](/windows/desktop/Midl/helpfile) описании атрибута MIDL.

## <a name="example"></a>Пример

См. в примере [модуль](module-cpp.md) пример демонстрирует использование **helpfile**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**интерфейс**, **typedef**, **класс**, метод, **свойство**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты интерфейса](interface-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты метода](method-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)  