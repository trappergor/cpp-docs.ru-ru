---
title: db_table (атрибут COM C++)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_table
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
ms.openlocfilehash: 9e05a980764b8b97f6c774165fdddd5428a0c989
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215287"
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

*состав*<br/>
Определяет переменную, которая будет получать HRESULT от этой команды базы данных (необязательно). Если переменная не существует, она будет автоматически внедрена с помощью атрибута.

## <a name="remarks"></a>Remarks

**db_table** создает объект [CTable](../../data/oledb/ctable-class.md) , который используется потребителем OLE DB для открытия таблицы. Этот атрибут можно использовать только на уровне класса. его нельзя использовать в строке. Используйте `db_column` для привязки столбцов таблицы к переменным; используйте `db_param` для разделения (задайте тип параметра и т. д.) для параметров.

Если поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс в \_*YourClassName*Accessor, где *YourClassName* — это имя, которое вы присвоили классу. Также компилятор создаст класс с именем *YourClassName*, производный от \_*YourClassName*Accessor.  В представлении классов отображаются оба класса.

## <a name="example"></a>Пример

В следующем примере открывается таблица Products для использования в `CProducts` .

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
|**Относится к**|**`class`**, **`struct`**|
|**REPEATABLE**|Нет|
|**Требуемые атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[OLE DB атрибуты потребителя](ole-db-consumer-attributes.md)
