---
title: db_table | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_table
dev_langs:
- C++
helpviewer_keywords:
- db_table attribute
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6e084a0f876d0b2598a5317e15057162c602474a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717123"
---
# <a name="dbtable"></a>db_table

Открывает таблицу OLE DB.

## <a name="syntax"></a>Синтаксис

```cpp
[ db_table(
   db_table,
   name,
   source_name,
   hresult
) ]
```

#### <a name="parameters"></a>Параметры

*db_table*  
Строка, указывающая имя таблицы базы данных (например, «продукты»).

*name*  
(Необязательно) Имя дескриптора, который можно использовать для работы с таблицей. Необходимо указать этот параметр, если вы хотите вернуть более одной строки результатов. **db_table** создает переменную с указанным *имя* , может использоваться для просмотра набора строк или выполнения нескольких запросов.

*source_name*  
(Необязательно) `CSession` Переменной или экземпляр класса, который имеет `db_source` атрибут, примененный к нему, на котором выполняется команда. См. описание [db_source](../windows/db-source.md).

*значение HRESULT*  
(Необязательно) Определяет переменную, которая будет получать значение HRESULT, равное этой команды базы данных. Если переменная не существует, она будет автоматически внедрена с помощью атрибута.

## <a name="remarks"></a>Примечания

**db_table** создает [CTable](../data/oledb/ctable-class.md) объект, который используется потребителем OLE DB для открытия таблицы. Этот атрибут можно использовать только на уровне класса; его нельзя использовать встроенные. Используйте `db_column` для привязки столбцов таблицы к переменным; используйте `db_param` в качестве разделителя (заданное тип параметра и поэтому в) параметров.

Когда поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс \_ *Имя_вашего_класса*метод доступа, где *Имя_вашего_класса* — это имя, присвоенное класс, компилятор также создаст класс с именем *Имя_вашего_класса*, который является производным от \_ *имя_класса*метода доступа.  В представлении классов отображаются оба класса.

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

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).

## <a name="see-also"></a>См. также

[Атрибуты объекта-получателя OLE DB](../windows/ole-db-consumer-attributes.md)  
