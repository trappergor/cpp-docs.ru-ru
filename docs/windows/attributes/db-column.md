---
title: db_column (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_column
dev_langs:
- C++
helpviewer_keywords:
- db_column attribute
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 52b5c5bea282e4ebb4106d8e9c2fede40f375ae3
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083617"
---
# <a name="dbcolumn"></a>db_column

Привязывает указанный столбец к переменной в наборе строк.

## <a name="syntax"></a>Синтаксис

```cpp
[ db_column(ordinal, dbtype, precision, scale, status, length) ]
```

#### <a name="parameters"></a>Параметры

*Порядковый номер*<br/>
Порядковый номер столбца (`DBCOLUMNINFO` порядковый номер) или имя столбца (строка ANSI или Юникод), соответствующее поле в наборе строк, к которому требуется привязать данные. Если вы используете номера, можно пропустить последовательных порядковые номера (например: 1, 2, 3, 5). Имя может содержать пробелы, если используемый поставщик OLE DB поддерживает его. Например можно использовать любой из следующих форматов:

```cpp
[db_column("2")] TCHAR szCity[30];
[db_column(L"city_name")] TCHAR szCity[30];
```

*dbType*<br/>
(Необязательно) OLE DB [индикатор типа](/previous-versions/windows/desktop/ms711251) для записи в столбце.

*precision*<br/>
(Необязательно) Точность должна использоваться для записи в столбце. Дополнительные сведения см. в описании `bPrecision` элемент [структуры DBBINDING](/previous-versions/windows/desktop/ms716845)

*Масштаб*<br/>
(Необязательно) Масштабирования, которая будет использоваться для записи в столбце. Дополнительные сведения см. в описании `bScale` элемент [структуры DBBINDING](/previous-versions/windows/desktop/ms716845)

*status*<br/>
(Необязательно) Переменную-член используется для хранения состояния этого столбца. Состояние указывает, является ли значение столбца значение данных или любое другое значение, например значений NULL. Возможные значения см. в разделе [состояние](/previous-versions/windows/desktop/ms722617) в *Справочник программиста OLE DB по*.

*length*<br/>
(Необязательно) Переменную-член используется для хранения размера столбца в байтах.

## <a name="remarks"></a>Примечания

**db_column** связывает указанного табличного столбца с переменной в наборе строк. Она разделяет данные члена, которые могут участвовать в OLE DB `IAccessor`-привязку на основе. Этот атрибут задает сопоставление столбцов, обычно определяется с помощью макросов потребителя OLE DB [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md), [END_COLUMN_MAP](../../data/oledb/end-column-map.md), и [COLUMN_ENTRY](../../data/oledb/column-entry.md). Эти управления OLE DB [структуры DBBINDING](/previous-versions/windows/desktop/ms716845) для привязки указанного столбца. Каждый член, пометьте с **db_column** атрибут будет занимать одну запись в сопоставлении столбцов в виде записи в столбце. Следовательно вызывать этот атрибут где находится в сопоставление столбцов, то есть в классе команд или таблиц.

Используйте **db_column** в сочетании со [db_table](db-table.md) или [db_command](db-command.md) атрибуты.

Когда поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс \_ *Имя_вашего_класса*метод доступа, где *Имя_вашего_класса* — это имя, присвоенное класс, компилятор также создаст класс с именем *Имя_вашего_класса*, который является производным от \_ *имя_класса*метода доступа.  В представлении классов отображаются оба класса.

Примеры использования этого атрибута, используемые в приложениях, см. Примеры [AtlAgent](https://github.com/Microsoft/VCSamples), и [MultiRead](https://github.com/Microsoft/VCSamples).

## <a name="example"></a>Пример

В этом образце привязки к столбцу в таблице, чтобы **long** член данных с указанием состояния и длины поля.

```cpp
// db_column_1.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_command(L"Select * from Products") ]
class CProducts {
   DBSTATUS m_dwProductIDStatus;
   DBLENGTH m_dwProductIDLength;

   [ db_column("1", status="m_dwProductIDStatus", length="m_dwProductIDLength") ] LONG m_ProductID;
};
```

## <a name="example"></a>Пример

В этом примере привязывает четыре столбца, **long**, символьная строка, метку времени и `DB_NUMERIC` целое число, в указанном порядке.

```cpp
// db_column_2.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_command(L"Select * from Products") ]
class CProducts {
   [db_column("1")] LONG m_OrderID;
   [db_column("2")] TCHAR m_CustomerID[6];
   [db_column("4")] DB_NUMERIC m_OrderDate;
   [db_column("7", dbtype="DBTYPE_NUMERIC")] DB_NUMERIC m_ShipVia;
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**, элемент, метод|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты объекта-получателя OLE DB](ole-db-consumer-attributes.md)<br/>
[Атрибуты классов](class-attributes.md)  
