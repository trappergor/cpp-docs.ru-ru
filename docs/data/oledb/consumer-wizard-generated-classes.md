---
title: Классы, создаваемые мастером объекта-получателя
ms.date: 10/17/2018
helpviewer_keywords:
- attribute-injected classes and methods
- wizard-generated classes and methods
- OLE DB consumers, wizard-generated classes and methods
- command classes in OLE DB consumer
- classes [C++], OLE DB Consumer Wizard-generated
- consumer wizard-generated classes and methods
- user record classes in OLE DB consumer
ms.assetid: dba0538f-2afe-4354-8cbb-f202ea8ade5a
ms.openlocfilehash: 7cd1fbe69186a2fcdbf25f1b2aa12727c98065da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62362247"
---
# <a name="consumer-wizard-generated-classes"></a>Классы, создаваемые мастером объекта-получателя

При использовании **Мастер потребителя ATL OLE DB** для создания объекта-получателя, вы можете выбрать с помощью шаблонов OLE DB или атрибутов OLE DB. В обоих случаях мастер создает класс команд и класс записей пользователя. В классе команд содержится код для открытия источника данных и набора строк, указанных в мастере. Класс записей пользователя содержит сопоставление столбцов для выбранной таблицы базы данных. Однако созданный код в каждом случае отличается.

- Если вы выбираете потребителя на основе шаблонов, мастер создает класс команд и класс записей пользователя. Класс команд будет иметь имя, введенное в **класс** поле в мастере (например, `CProducts`), и класс записей пользователя будет иметь имя в формате "*ClassName*метод доступа» (например, `CProductsAccessor`). Оба класса находятся в файле заголовка потребителя.

- При выборе потребителя на основе атрибутов класс записей пользователя будет иметь имя в форме "_*ИмяКласса*Accessor" и будет внедренным. То есть вы сможете просматривать только класс команд в текстовом редакторе; класс записей пользователя может только просматривать как внедренный код. Сведения о просмотре внедренного кода см. в разделе [Отладка внедренного кода](/visualstudio/debugger/how-to-debug-injected-code).

В следующих примерах используется класс команд, созданные на `Products` таблицу `Northwind` базы данных, чтобы продемонстрировать код создаваемого мастером потребителя класс команд и класс записей пользователя.

## <a name="templated-user-record-classes"></a>Классы записей пользователя на основе шаблонов

При создании потребителя OLE DB с помощью шаблонов OLE DB (а не атрибутов OLE DB) мастер создает код, как описано в этом разделе.

### <a name="column-data-members"></a>Элементы данных столбцов

Первая часть класса записей пользователя включает объявления элементов данных и элементы данных состояния и длины для каждого столбца с привязкой к данным. Сведения об этих элементах данных см. в разделе [Элементы данных состояния поля в создаваемых мастером методах доступа](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).

> [!NOTE]
> Если вы изменяете класс записей пользователя или создаете собственного потребителя, переменные данных должны находиться перед переменными состояния и длины.

> [!NOTE]
> Мастер потребителя ATL OLE DB использует `DB_NUMERIC` тип для привязки числовых типов данных. Ранее он использовал `DBTYPE_VARNUMERIC` (формат которого описывался `DB_VARNUMERIC` типа; см. Oledb.h). Если не используется мастер создания потребителей, рекомендуется использовать `DB_NUMERIC`.

```cpp
// Products.H : Declaration of the CProducts class

class CProductsAccessor
{
public:
   // Column data members:
   LONG m_ProductID;
   TCHAR m_ProductName[41];
   LONG m_SupplierID;
   LONG m_CategoryID;
   TCHAR m_QuantityPerUnit[21];
   CURRENCY m_UnitPrice;
   SHORT m_UnitsInStock;
   SHORT m_UnitsOnOrder;
   SHORT m_ReorderLevel;
   VARIANT_BOOL m_Discontinued;

   // Column status data members:
   DBSTATUS m_dwProductIDStatus;
   DBSTATUS m_dwProductNameStatus;
   DBSTATUS m_dwSupplierIDStatus;
   DBSTATUS m_dwCategoryIDStatus;
   DBSTATUS m_dwQuantityPerUnitStatus;
   DBSTATUS m_dwUnitPriceStatus;
   DBSTATUS m_dwUnitsInStockStatus;
   DBSTATUS m_dwUnitsOnOrderStatus;
   DBSTATUS m_dwReorderLevelStatus;
   DBSTATUS m_dwDiscontinuedStatus;

   // Column length data members:
   DBLENGTH m_dwProductIDLength;
   DBLENGTH m_dwProductNameLength;
   DBLENGTH m_dwSupplierIDLength;
   DBLENGTH m_dwCategoryIDLength;
   DBLENGTH m_dwQuantityPerUnitLength;
   DBLENGTH m_dwUnitPriceLength;
   DBLENGTH m_dwUnitsInStockLength;
   DBLENGTH m_dwUnitsOnOrderLength;
   DBLENGTH m_dwReorderLevelLength;
   DBLENGTH m_dwDiscontinuedLength;
```

### <a name="rowset-properties"></a>Свойства набора строк

Далее мастер задает свойства набора строк. Если в мастере потребителя ATL OLE DB вы выбрали **Изменить**, **Вставить**или **Удалить** , здесь задаются соответствующие свойства (свойство DBPROP_IRowsetChange всегда задается, а затем одно или несколько свойств DBPROPVAL_UP_CHANGE, DBPROPVAL_UP_INSERT или DBPROPVAL_UP_DELETE соответственно).

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet)
{
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
}
```

### <a name="command-or-table-class"></a>Класс команд или таблиц

Если вы указали класс команд, мастер объявляет класс команд; для кода на основе шаблонов команда выглядит следующим образом:

```cpp
DEFINE_COMMAND_EX(CProductsAccessor, L" \
SELECT \
   ProductID, \
   ProductName, \
   SupplierID, \
   CategoryID, \
   QuantityPerUnit, \
   UnitPrice, \
   UnitsInStock, \
   UnitsOnOrder, \
   ReorderLevel, \
   Discontinued \
   FROM dbo.Products")
```

### <a name="column-map"></a>Сопоставление столбцов

Затем мастер создает привязки столбцов или сопоставление столбцов. Для устранения некоторых проблем с поставщиками следующий код может привязывать столбцы в порядке, отличном от сообщаемого поставщиком.

```cpp
   BEGIN_COLUMN_MAP(CProductsAccessor)
      COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)
      COLUMN_ENTRY_LENGTH_STATUS(3, m_SupplierID, m_dwSupplierIDLength, m_dwSupplierIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(4, m_CategoryID, m_dwCategoryIDLength, m_dwCategoryIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(5, m_QuantityPerUnit, m_dwQuantityPerUnitLength, m_dwQuantityPerUnitStatus)
      _COLUMN_ENTRY_CODE(6, DBTYPE_CY, _SIZE_TYPE(m_UnitPrice), 0, 0, offsetbuf(m_UnitPrice), offsetbuf(m_dwUnitPriceLength), offsetbuf(m_dwUnitPriceStatus))
      COLUMN_ENTRY_LENGTH_STATUS(7, m_UnitsInStock, m_dwUnitsInStockLength, m_dwUnitsInStockStatus)
      COLUMN_ENTRY_LENGTH_STATUS(8, m_UnitsOnOrder, m_dwUnitsOnOrderLength, m_dwUnitsOnOrderStatus)
      COLUMN_ENTRY_LENGTH_STATUS(9, m_ReorderLevel, m_dwReorderLevelLength, m_dwReorderLevelStatus)
      _COLUMN_ENTRY_CODE(10, DBTYPE_BOOL, _SIZE_TYPE(m_Discontinued), 0, 0, offsetbuf(m_Discontinued), offsetbuf(m_dwDiscontinuedLength), offsetbuf(m_dwDiscontinuedStatus))
   END_COLUMN_MAP()
};
```

### <a name="class-declaration"></a>Объявление класса

Наконец, мастер создает объявление класса команд, например следующим образом:

```cpp
class CProducts : public CCommand<CAccessor<CProductsAccessor>>
```

## <a name="attribute-injected-user-record-classes"></a>Классы записей пользователя, внедряемые атрибутами

Если вы создаете потребителя OLE DB с помощью атрибутов базы данных ([db_command](../../windows/db-command.md) или [db_table](../../windows/db-table.md)), эти атрибуты внедряют класс записей пользователя с именем в форме "_*ИмяКласса*Accessor". Например, если класс команд назван `COrders`, класс записей пользователя получит имя `_COrdersAccessor`. Несмотря на то, что класс записей пользователя отображается в **представление классов**, дважды щелкнув его вместо переходит к классу команд или таблиц в файле заголовка. В таких случаях вы можете просмотреть фактическое объявление класса записей пользователя только путем просмотра кода, внедренного атрибутами.

При добавлении или переопределении методов в потребителях на основе атрибутов могут возникать определенные сложности. Например, если вы добавите конструктор `_COrdersAccessor` в объявление `COrders` , то заметите, что в действительности конструктор добавляется во внедренный класс `COrdersAccessor` . Такой конструктор может инициализировать столбцы или параметры, но вам не удается создать конструктор копии таким образом, так как он не может напрямую создать экземпляр `COrdersAccessor` объекта. Если нужен конструктор (или другой метод) непосредственно в `COrders` класс, рекомендуется определить новый класс, наследуемый от `COrders` и добавить в него необходимые методы.

В следующем примере мастер создает объявление класса `COrders`, но класс записей пользователя `COrdersAccessor` не отображается, поскольку его вводит атрибут.

```cpp
#define _ATL_ATTRIBUTES
#include <atlbase.h>
#include <atldbcli.h>
[
   db_source(L"your connection string"),
   db_command(L"Select ShipName from Orders;")
]
class COrders
{
public:

   // COrders()            // incorrect constructor name
   _COrdersAccessor()      // correct constructor name
   {
   }
      [db_column(1) ] TCHAR m_ShipName[41];
   };
```

Объявление внедренного класса команд выглядит следующим образом:

```cpp
class CProducts : public CCommand<CAccessor<_CProductsAccessor>>
```

Большая часть внедренного кода аналогична версии на основе шаблона. Основные различия — во внедренных методах, которые описаны в разделе [Методы, создаваемые мастером потребителя](../../data/oledb/consumer-wizard-generated-methods.md).

Сведения о просмотре внедренного кода см. в разделе [Отладка внедренного кода](/visualstudio/debugger/how-to-debug-injected-code).

## <a name="see-also"></a>См. также

[Создание объекта-получателя OLE DB с помощью мастера](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)