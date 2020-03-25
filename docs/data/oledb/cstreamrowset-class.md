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
ms.openlocfilehash: 300933fd6d10f5da39d9276db746ab789851a9a1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211176"
---
# <a name="cstreamrowset-class"></a>Класс CStreamRowset

Используется в объявлении `CCommand` или `CTable`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class TAccessor = CAccessorBase>
class CStreamRowset
```

### <a name="parameters"></a>Параметры

*такцессор*<br/>
Класс метода доступа.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Члены

### <a name="methods"></a>Методы

|||
|-|-|
|[CStreamRowset](#cstreamrowset)|Конструктор. Создает и инициализирует объект `CStreamRowset`.|
|[Закрыть](#close)|Освобождает указатель интерфейса [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) в классе.|

## <a name="remarks"></a>Remarks

Используйте `CStreamRowset` в объявлении `CCommand` или `CTable`, например:

[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]

или диспетчер конфигурации служб

[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]

`ICommand::Execute` возвращает указатель `ISequentialStream`, хранящийся в `m_spStream`. Затем используется метод `Read` для получения данных (строки в Юникоде) в формате XML. Пример:

[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]

SQL Server 2000 выполняет форматирование XML и будет возвращать все столбцы и все строки набора строк в виде одной строки XML.

> [!NOTE]
>  Эта функция работает только с SQL Server 2000.

## <a name="cstreamrowsetcstreamrowset"></a><a name="cstreamrowset"></a>CStreamRowset:: CStreamRowset

Создает и инициализирует объект `CStreamRowset`.

### <a name="syntax"></a>Синтаксис

```cpp
CStreamRowset();
```

## <a name="cstreamrowsetclose"></a><a name="close"></a>CStreamRowset:: Close

Освобождает указатель интерфейса [ISequentialStream](/previous-versions/windows/desktop/ms718035(v=vs.85)) в классе.

### <a name="syntax"></a>Синтаксис

```cpp
void Close();
```

## <a name="see-also"></a>См. также раздел

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)
