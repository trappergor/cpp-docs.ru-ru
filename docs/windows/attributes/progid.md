---
title: ProgID (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.progid
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
ms.openlocfilehash: d529d7362dc62207cfd72576159f560a3e04c221
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514251"
---
# <a name="progid"></a>progid

Указывает ProgID для COM-объекта.

## <a name="syntax"></a>Синтаксис

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>Параметры

*name*<br/>
Идентификатор ProgID, представляющий объект.

Идентификаторы ProgID представляют собой удобочитаемую для человека версию идентификатора класса (CLSID), используемую для идентификации объектов COM/ActiveX.

## <a name="remarks"></a>Примечания

Атрибут **ProgID** C++ позволяет указать ProgID для COM-объекта. Идентификатор ProgID имеет форму *name1. имя2. Version*. Если не указать *версию* для ProgID, используется версия по умолчанию 1. Если не указать *name1. имя2*, по умолчанию используется имя *className. ClassName*. Если параметр **ProgID** не указан и указано `vi_progid`, *name1. имя2* берется из `vi_progid` и добавляется версия (следующий последовательный номер).

Если блок атрибута, использующий **ProgID** , не использует **UUID**, Компилятор проверит реестр на наличие **UUID** для указанного **ProgID**. Если параметр **ProgID** не указан, для создания **идентификатора ProgID**будет использоваться версия (и имя кокласса, если создается coclass).

**ProgID** подразумевает `coclass` атрибут, то есть при указании **ProgID**это `coclass` то же самое, что и указание атрибутов и **ProgID** .

Атрибут **ProgID** вызывает автоматическую регистрацию класса с указанным именем. Созданный IDL-файл не будет отображать значение **ProgID** .

Если этот атрибут используется в проекте, использующем ATL, поведение атрибута изменяется. В дополнение к описанному выше поведению, сведения, указанные с помощью этого атрибута, `GetProgID` используются в функции, внедренной `coclass` атрибутом. Дополнительные сведения см. в описании атрибута [coclass](coclass.md) .

## <a name="example"></a>Пример

Пример использования **ProgID**см. в примере для [coclass](coclass.md) .

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
[Атрибуты классов](class-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Ключ ProgID](/windows/win32/com/-progid--key)
