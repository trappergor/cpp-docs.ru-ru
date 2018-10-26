---
title: Класс CColumnAccessor | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
dev_langs:
- C++
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1e55d4c15ca5d5a3733c44cf89b788b85c905513
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074674"
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