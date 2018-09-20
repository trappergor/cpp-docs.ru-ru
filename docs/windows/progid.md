---
title: Идентификатор ProgID | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.progid
dev_langs:
- C++
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 337972b9659ae32e2ea40e12d6301cc1f0c9aba7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408002"
---
# <a name="progid"></a>progid

Указывает идентификатор ProgID для COM-объекта.

## <a name="syntax"></a>Синтаксис

```cpp
[ progid(
   name
) ];
```

### <a name="parameters"></a>Параметры

*name*<br/>
Идентификатор ProgID, представляющий объект.

Идентификаторы ProgID представляют удобное для восприятия версию идентификатор класса (CLSID), используемый для идентификации объектов COM/ActiveX.

## <a name="remarks"></a>Примечания

**Progid** C++ атрибут позволяет указать идентификатор ProgID для COM-объекта. Идентификатор ProgID имеет форму *name1.name2.version*. Если вы не укажете *версии* для ProgID, версия по умолчанию — 1. Если вы не укажете *name1.name2*, имя по умолчанию — *classname.classname*. Если вы не укажете **progid** и указать `vi_progid`, *name1.name2* берутся из `vi_progid` и (порядковый номер) версии добавляется.

Если в блоке атрибута, который использует **progid** также не используйте **uuid**, тогда компилятор проверит реестр ли **uuid** существует для указанного **progid** . Если **progid** не указан, версии (и имя компонентного класса, если создание компонентного класса) будет использоваться для создания **progid**.

**Идентификатор ProgID** подразумевает `coclass` атрибута, то есть, если указать **progid**, это то же самое, что и указание `coclass` и **progid** атрибуты.

**Progid** атрибут заставляет класс автоматически регистрироваться под указанным именем. Созданного IDL-файла не отобразит **progid** значение.

Если этот атрибут используется в проекте, где применяется ATL, поведение атрибута изменяется. Помимо описанного выше поведения, сведений, указанных с помощью этого атрибута используется в `GetProgID` функции, введенному `coclass` атрибута. Дополнительные сведения см. в разделе [coclass](../windows/coclass.md) атрибута.

## <a name="example"></a>Пример

См. в примере [coclass](../windows/coclass.md) использовать образец **progid**.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты IDL](../windows/idl-attributes.md)<br/>
[Атрибуты классов](../windows/class-attributes.md)<br/>
[Атрибуты Typedef, Enum, Union и Struct](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[Идентификатор progID ключ](/windows/desktop/com/-progid--key)  
