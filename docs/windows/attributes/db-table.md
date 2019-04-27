---
title: db_table (C++ атрибут COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_table
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
ms.openlocfilehash: 3ab548261d6ebcb9d3d7f7e352c8afe3b33db06f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148124"
---
# <a name="dbtable"></a>db_table

Открывает таблицу OLE DB.

## <a name="syntax"></a>Синтаксис

```cpp
[ db_table(db_table, name, source_name, hresult) ]
```

#### <a name="parameters"></a>Параметры

*db_table*<br/>
Строка, указывающая имя таблицы базы данных (например, «продукты»).

*name*<br/>
(Необязательно) Имя дескриптора, который можно использовать для работы с таблицей. Необходимо указать этот параметр, если вы хотите вернуть более одной строки результатов. **db_table** создает переменную с указанным *имя* , может использоваться для просмотра набора строк или выполнения нескольких запросов.

*source_name*<br/>
Переменная `CSession` или экземпляр класса с примененным атрибутом `db_source`, по которому выполняется команда (необязательно). См. описание [db_source](db-source.md).

*hresult*<br/>
Определяет переменную, которая будет получать HRESULT от этой команды базы данных (необязательно). Если переменная не существует, она будет автоматически внедрена с помощью атрибута.

## <a name="remarks"></a>Примечания

**db_table** создает [CTable](../../data/oledb/ctable-class.md) объект, который используется потребителем OLE DB для открытия таблицы. Этот атрибут можно использовать только на уровне класса; его нельзя использовать встроенные. Используйте `db_column` для привязки столбцов таблицы к переменным; используйте `db_param` в качестве разделителя (заданное тип параметра и поэтому в) параметров.

Если поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс в \_*YourClassName*Accessor, где *YourClassName* — это имя, которое вы присвоили классу. Также компилятор создаст класс с именем *YourClassName*, производный от \_*YourClassName*Accessor.  В представлении классов отображаются оба класса.

## <a name="example"></a>Пример

В следующем примере открывается в таблице продуктов для использования `CProducts`.

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

Пример того, этот атрибут, используемый в приложении, см. в примерах [AtlAgent](https://github.com/Microsoft/VCSamples) и [MultiRead](https://github.com/Microsoft/VCSamples).

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**Класс**, **структуры**|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты объекта-получателя OLE DB](ole-db-consumer-attributes.md)
