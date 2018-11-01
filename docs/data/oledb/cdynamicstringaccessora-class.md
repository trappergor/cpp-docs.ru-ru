---
title: Класс CDynamicStringAccessorA
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorA
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
ms.openlocfilehash: bfe4cf2d6aa107c21ed0d8b226616ebaa8488102
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537440"
---
# <a name="cdynamicstringaccessora-class"></a>Класс CDynamicStringAccessorA

Позволяет доступ к источнику данных, когда схема базы данных (базовая структура).

## <a name="syntax"></a>Синтаксис

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;
```

## <a name="remarks"></a>Примечания

Они оба запроса, что поставщик получить все данные из хранилища данных в виде строковых данных, но `CDynamicStringAccessor` запросы ANSI строковые данные.

`CDynamicStringAccessorA` наследует `GetString` и `SetString` из `CDynamicStringAccessor`. При использовании этих методов в `CDynamicStringAccessorA` объекта, `BaseType` — **CHAR**.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс CAccessor](../../data/oledb/caccessor-class.md)<br/>
[Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)<br/>
[Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
[Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
