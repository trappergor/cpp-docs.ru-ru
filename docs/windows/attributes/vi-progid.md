---
title: vi_progid (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.vi_progid
dev_langs:
- C++
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b63e98e070dc5352d7c1456252722bea958b8bf
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072100"
---
# <a name="viprogid"></a>vi_progid

Указывает форму независящим от версии идентификатор ProgID.

## <a name="syntax"></a>Синтаксис

```cpp
[ vi_progid(name) ];
```

### <a name="parameters"></a>Параметры

*name*<br/>
Идентификатор ProgID независящим от версии, представляющий объект.

Идентификаторы ProgID представляют удобное для восприятия версию идентификатор класса (CLSID), используемый для идентификации объектов COM/ActiveX.

## <a name="remarks"></a>Примечания

**Vi_progid** C++ атрибут позволяет указать независящим от версии идентификатор ProgID COM-объекта. Идентификатор ProgID имеет форму *name1.name2.version*. Независимый от версии идентификатор ProgID не поддерживает *версии*. Можно указать оба `progid` и **vi_progid** атрибуты `coclass`. Если вы не укажете **vi_progid**, независимые от версии идентификатор ProgID — значение, заданное параметром [progid](progid.md) атрибута.

**vi_progid** подразумевает `coclass` атрибута, то есть, если указать **vi_progid**, это то же самое, что и указание `coclass` и **vi_progid** атрибуты.

**Vi_progid** атрибут заставляет класс автоматически регистрироваться под указанным именем. Созданного IDL-файла не будет отображать ProgID значение.

В проектах ATL Если [coclass](coclass.md) присутствует также атрибут, используемый указанным идентификатором ProgID `GetVersionIndependentProgID` функция (вставленные `coclass` атрибут).

## <a name="example"></a>Пример

См. в разделе [coclass](coclass.md) пример для использовать **vi_progid**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](typedef-enum-union-and-struct-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)<br/>
[Идентификатор progID ключ](/windows/desktop/com/-progid--key)
