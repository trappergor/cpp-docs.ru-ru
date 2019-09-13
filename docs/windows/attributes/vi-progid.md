---
title: vi_progid (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.vi_progid
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
ms.openlocfilehash: fbf5ab2bc4263356a1cfcf789865a3f7e286ccd7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514867"
---
# <a name="vi_progid"></a>vi_progid

Указывает независимую от версии форму ProgID.

## <a name="syntax"></a>Синтаксис

```cpp
[ vi_progid(name) ];
```

### <a name="parameters"></a>Параметры

*name*<br/>
Идентификатор ProgID, не зависящий от версии, представляющий объект.

Идентификаторы ProgID представляют собой удобочитаемую для человека версию идентификатора класса (CLSID), используемую для идентификации объектов COM/ActiveX.

## <a name="remarks"></a>Примечания

Атрибут **vi_progid** C++ позволяет указать независимый от версии идентификатор ProgID для COM-объекта. Идентификатор ProgID имеет форму *name1. имя2. Version*. Идентификатор ProgID, не зависящий от версии, не имеет *версии*. В можно указать `progid` и атрибуты `coclass`, и **vi_progid** . Если не указать **vi_progid**, идентификатор ProgID, не зависящий от версии, является значением, заданным атрибутом [ProgID](progid.md) .

**vi_progid** подразумевает `coclass` атрибут, то есть если указать **vi_progid**, то это `coclass` то же самое, что и атрибуты и **vi_progid** .

Атрибут **vi_progid** вызывает автоматическую регистрацию класса с указанным именем. Созданный IDL-файл не будет отображать значение ProgID.

В проектах ATL, если атрибут [coclass](coclass.md) также имеется, указанный идентификатор ProgID используется `GetVersionIndependentProgID` функцией `coclass` (которая вставляется атрибутом).

## <a name="example"></a>Пример

Пример использования **vi_progid**см. в примере [компонентного класса](coclass.md) .

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Относится к**|**класс**, **Структура**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Отсутствуют|
|**Недопустимые атрибуты**|Отсутствуют|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Ключ ProgID](/windows/win32/com/-progid--key)
