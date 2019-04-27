---
title: Класс CDynamicStringAccessorW
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorW
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
ms.openlocfilehash: 20ea4a2d795108e00c4b11c3abea6cf7b9953ca7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230792"
---
# <a name="cdynamicstringaccessorw-class"></a>Класс CDynamicStringAccessorW

Позволяет доступ к источнику данных, когда схема базы данных (базовая структура).

## <a name="syntax"></a>Синтаксис

```cpp
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;
```

## <a name="remarks"></a>Примечания

Они оба запроса, что поставщик получить все данные из хранилища данных в виде строковых данных, но `CDynamicStringAccessor` запрашивает строки в Юникоде.

`CDynamicStringAccessorW` наследует `GetString` и `SetString` из `CDynamicStringAccessor`. При использовании этих методов в `CDynamicStringAccessorW` объекта, `BaseType` — **WCHAR**.

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
