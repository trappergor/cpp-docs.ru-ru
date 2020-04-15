---
title: Класс CStreamRowset
ms.date: 11/04/2016
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
- CStreamRowset::CStreamRowset
- CStreamRowset.CStreamRowset
- ATL.CStreamRowset.CStreamRowset
- ATL::CStreamRowset::CStreamRowset
- CStreamRowset<TAccessor>::CStreamRowset
- ATL::CStreamRowset<TAccessor>::CStreamRowset
- CStreamRowset<TAccessor>.Close
- ATL.CStreamRowset<TAccessor>.Close
- CStreamRowset::Close
- CStreamRowset<TAccessor>::Close
- ATL::CStreamRowset::Close
- ATL.CStreamRowset.Close
- ATL::CStreamRowset<TAccessor>::Close
- CStreamRowset.Close
helpviewer_keywords:
- CStreamRowset class
- CStreamRowset class, constructor
- Close method
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
ms.openlocfilehash: ad4987422fd200faef141150908d4df0722f669a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366276"
---
# <a name="cstreamrowset-class"></a>Класс CStreamRowset

Используется в `CCommand` `CTable` декларации или декларации.

## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CAccessorBase>
class CStreamRowset
```

### <a name="parameters"></a>Параметры

*TAccessor*<br/>
Класс аксессуаров.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CStreamRowset](#cstreamrowset)|Конструктор. Мгновения и инициализации `CStreamRowset` объекта.|
|[Закрыть](#close)|Выпускает указатель интерфейса [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) в классе.|

## <a name="remarks"></a>Remarks

Используйте `CStreamRowset` `CCommand` в `CTable` своей или декларации, например:

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

or

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute`возвращает `ISequentialStream` указатель, который хранится в `m_spStream`. Затем `Read` метод для извлечения данных (строки Unicode) в формате XML. Пример:

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

S'L Server 2000 выполняет форматирование XML и возвращает все столбцы и все строки строки строки в виде одной строки XML.

> [!NOTE]
> Эта функция работает только с сервером S'L Server 2000.

## <a name="cstreamrowsetcstreamrowset"></a><a name="cstreamrowset"></a>CStreamRowset::CStreamRowset

Мгновения и инициализации `CStreamRowset` объекта.

### <a name="syntax"></a>Синтаксис

```cpp
CStreamRowset();
```

## <a name="cstreamrowsetclose"></a><a name="close"></a>CStreamRowset::Закрыть

Выпускает указатель интерфейса [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) в классе.

### <a name="syntax"></a>Синтаксис

```cpp
void Close();
```

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[СПРАВКа о потребительских шаблонах OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
