---
title: HelpFile (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpfile
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
ms.openlocfilehash: 538cdbb38ac525cfee03a641f3e62e22a69f8e2b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501542"
---
# <a name="helpfile"></a>helpfile

Задает имя файла справки для библиотеки типов.

## <a name="syntax"></a>Синтаксис

```cpp
[ helpfile("filename") ]
```

### <a name="parameters"></a>Параметры

*filename*<br/>
Имя файла, содержащего разделы справки.

## <a name="remarks"></a>Примечания

Атрибут **HelpFile** C++ имеет те же функциональные возможности, что и атрибут [HelpFile](/windows/win32/Midl/helpfile) MIDL.

## <a name="example"></a>Пример

Пример использования **HelpFile**см. в примере для [модуля](module-cpp.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**Interface**, **typedef**, **класс**, метод, **свойство**|
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
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)