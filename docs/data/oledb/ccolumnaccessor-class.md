---
title: Класс CColumnAccessor
ms.date: 11/04/2016
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
ms.openlocfilehash: 85d3d9d4339634ea7948d7d5e9e09725b7fd8758
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611372"
---
# <a name="ccolumnaccessor-class"></a>Класс CColumnAccessor

Создает код внедренного объекта-получателя.

## <a name="syntax"></a>Синтаксис

```cpp
class CColumnAccessor : public CAccessorBase
```

## <a name="remarks"></a>Примечания

В этот код каждый столбец привязан как отдельный метод доступа. Следует иметь в виду, что этот класс используется в введенного кода (например, вы можете столкнуться его при отладке), но обычно никогда не требуется напрямую использовать его, или его методы.

`CColumnAccessor` реализует следующие методы-заглушки, каждый из которых соответствует функциональности к другим методам класса метода доступа:

- `CColumnAccessor` Конструктор. Создает и инициализирует `CColumnAccessor` объекта.

- `CreateAccessor` Выделяет память для столбца структуры привязки и инициализирует элементы данных столбцов.

- `BindColumns` Привязывает столбцы к методы доступа.

- `SetParameterBuffer` Выделяет буферы для параметров.

- `AddParameter` Добавляет запись параметра запись на параметр структуры.

- `HasOutputColumns` Определяет, является ли метод доступа содержит выходные столбцы

- `HasParameters` Определяет, имеет ли метод доступа параметров.

- `BindParameters` Связывает созданный параметры к столбцам.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)