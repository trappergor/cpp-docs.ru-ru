---
title: db_table (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_table
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
ms.openlocfilehash: 2b3be55a4ea118ef3441d3ea93f63e19ebdb3d79
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167255"
---
# <a name="db_table"></a>db_table

Открывает таблицу OLE DB.

## <a name="syntax"></a>Синтаксис

```cpp
[ db_table(db_table, name, source_name, hresult) ]
```

### <a name="parameters"></a>Параметры

*db_table*<br/>
Строка, указывающая имя таблицы базы данных (например, "Products").

*name*<br/>
Используемых Имя маркера, используемого для работы с таблицей. Этот параметр необходимо указать, если требуется вернуть более одной строки результатов. **db_table** создает переменную с указанным *именем* , которую можно использовать для прохода по набору строк или выполнения нескольких запросов на изменение.

*source_name*<br/>
Переменная `CSession` или экземпляр класса с примененным атрибутом `db_source`, по которому выполняется команда (необязательно). См. описание [db_source](db-source.md).

*hresult*<br/>
Определяет переменную, которая будет получать HRESULT от этой команды базы данных (необязательно). Если переменная не существует, она будет автоматически внедрена с помощью атрибута.

## <a name="remarks"></a>Remarks

**db_table** создает объект [CTable](../../data/oledb/ctable-class.md) , который используется потребителем OLE DB для открытия таблицы. Этот атрибут можно использовать только на уровне класса. его нельзя использовать в строке. Используйте `db_column` для привязки столбцов таблицы к переменным; Используйте `db_param` для разделения параметров (задайте тип параметра и т. д.).

Если поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс в \_*YourClassName*Accessor, где *YourClassName* — это имя, которое вы присвоили классу. Также компилятор создаст класс с именем *YourClassName*, производный от \_*YourClassName*Accessor.  В представлении классов отображаются оба класса.

## <a name="example"></a>Пример

В следующем примере открывается таблица Products для использования `CProducts`.

```cpp
// db_table.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[ db_table(L"dbo.Products") ]
class CProducts {
   [ db_column("1") ] LONG m_ProductID;
};
```

Пример использования этого атрибута в приложении см. в разделе [Read](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer).

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**класс**, **Структура**|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты объекта-получателя OLE DB](ole-db-consumer-attributes.md)
