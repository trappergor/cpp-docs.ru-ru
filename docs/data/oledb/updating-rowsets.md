---
title: обновление наборов строк
ms.date: 05/09/2019
helpviewer_keywords:
- rowsets, updating data
- updating data, rowsets
- updating rowsets
- rowsets
ms.assetid: 39588758-5c72-4254-a10d-cc2b1f473357
ms.openlocfilehash: 22e362170d645574b40070c6db39c2576d3ae9c8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212947"
---
# <a name="updating-rowsets"></a>обновление наборов строк

Обновление или запись данных в хранилище данных — одна из основных операций баз данных. В OLE DB используется простой механизм обновления: приложение-клиент задает значения привязанных членов данных, а затем записывает эти значения в набор строк; затем клиент запрашивает у поставщика обновление хранилища данных.

Клиенты могут выполнять следующие типы обновлений в данных набора строк: задание значений столбцов в строке, вставку строки и удаление строки. Чтобы можно было использовать эти операции, класс шаблона OLE DB [CRowset](../../data/oledb/crowset-class.md) реализует интерфейс [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) и переопределяет следующие методы интерфейса:

- команда [SetData](../../data/oledb/crowset-setdata.md) изменяет значения столбцов в строке или наборе строк (соответствует команде SQL UPDATE);

- команда [Insert](../../data/oledb/crowset-insert.md) вставляет строку в набор строк (соответствует команде SQL INSERT);

- команда [Delete](../../data/oledb/crowset-delete.md) удаляет строки из набора строк (соответствует команде SQL DELETE).

## <a name="supporting-update-operations"></a>Поддержка операций обновления

> [!NOTE]
> Мастер объекта-получателя ATL OLE DB недоступен в Visual Studio 2019 и более поздних версиях. Эту функцию все еще можно добавить вручную. Дополнительные сведения см. в статье [Создание объекта-получателя без помощи мастера](creating-a-consumer-without-using-a-wizard.md).

При создании потребителя с помощью **мастера ATL OLE DB Consumer**можно поддерживать операции обновления, выбрав один или несколько из трех флажков **изменить**, **Вставить**и **Удалить**. При их установке мастер изменяет код соответствующим образом, чтобы поддерживать выбранные типы изменений. Однако если вы не используете мастер, чтобы поддерживать обновления, вам потребуется задать значение `VARIANT_TRUE` следующим свойствам набора строк:

- `DBPROPVAL_UP_CHANGE` (позволяет изменять значения данных в строках);

- `DBPROPVAL_UP_INSERT` (позволяет вставить строку);

- `DBPROPVAL_UP_DELETE` (позволяет удалить строку).

Свойства задаются следующим образом.

```cpp
CDBPropSet ps(DBPROPSET_ROWSET);

ps.AddProperty(DBPROP_IRowsetChange, true);
ps.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
```

Операции изменения, вставки или удаления могут привести к сбою, если какие-то из столбцов не поддерживают запись. Измените схему курсоров, чтобы исправить это.

## <a name="setting-data-in-rows"></a>Задание данных в строках

[CRowset::SetData](../../data/oledb/crowset-setdata.md) задает значения данных в одном или нескольких столбцах текущей строки. Следующий код задает значения элементов данных, привязанных к столбцам `Name`, и `Units in Stock` таблиц `Products`, а затем вызывает `SetData`, чтобы записать эти значения в сотую строку набора строк.

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Change the values of columns "Name" and "Units in Stock" in the current row of the Product table
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Candle" ) );

product.m_UnitsInStock = 10000;

// Set the data
HRESULT hr = product.SetData();
```

## <a name="inserting-rows-into-rowsets"></a>Вставка строк в наборы строк

[CRowset::Insert](../../data/oledb/crowset-insert.md) создает и инициализирует новую строку, используя данные из метода доступа. `Insert` создает новую строку после текущей. Вам нужно указать, следует ли перейти с текущей строки на следующую или оставить выбор текущей строки без изменений. Это можно сделать, задав параметр *bGetRow* :

```cpp
HRESULT Insert(int nAccessor = 0, bool bGetRow = false)
```

- **`false`**(значение по умолчанию) указывает, что текущая строка увеличивается до следующей строки (в этом случае она указывает на вставленную строку).

- **`true`** Указывает, что текущая строка остается в том месте, где она находится.

Следующий код задает значения элементов данных, привязанных к столбцам таблицы `Products`, а затем вызывает `Insert`, чтобы вставить новую строку с этими значениями после сотой строки набора строк. Рекомендуется задать все значения столбцов, чтобы избежать появления неопределенных данных в новой строке.

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Set the column values for a row of the Product table, then insert the row
product.m_ProductID = 101;
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Candle" ) );

product.m_SupplierID = 27857;
product.m_CategoryID = 372;
_tcscpy_s(product.m_QuantityPerUnit, product.m_sizeOfQuantityPerUnit, _T( "Pack of 10" ) );

product.m_UnitPrice = 20;
product.m_UnitsInStock = 10000;
product.m_UnitsOnOrder = 5201;
product.m_ReorderLevel = 5000;
product.m_Discontinued = false;

// You must also initialize the status and length fields before setting/inserting data
// Set the column status values
m_dwProductIDStatus = DBSTATUS_S_OK;
m_dwProductNameStatus = DBSTATUS_S_OK;
m_dwSupplierIDStatus = DBSTATUS_S_OK;
m_dwCategoryIDStatus = DBSTATUS_S_OK;
m_dwQuantityPerUnitStatus = DBSTATUS_S_OK;
m_dwUnitPriceStatus = DBSTATUS_S_OK;
m_dwUnitsInStockStatus = DBSTATUS_S_OK;
m_dwUnitsOnOrderStatus = DBSTATUS_S_OK;
m_dwReorderLevelStatus = DBSTATUS_S_OK;
m_dwDiscontinuedStatus = DBSTATUS_S_OK;

// Set the column length value for column data members that are not fixed-length types.
// The value should be the length of the string that you are setting.
m_dwProductNameLength = 6;             // "Candle" has 6 characters
m_dwQuantityPerUnitLength = 10;        // "Pack of 10" has 10 characters

// Insert the data
HRESULT hr = product.Insert();
```

Более подробный пример см. в описании [CRowset::Insert](../../data/oledb/crowset-insert.md).

Дополнительные сведения о задании членов данных состояния и длины см. в разделе [Члены данных состояния поля в методах доступа, созданных мастером](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).

## <a name="deleting-rows-from-rowsets"></a>Удаление строк из наборов строк

[CRowset::Delete](../../data/oledb/crowset-delete.md) удаляет текущую строку из набора строк. Следующий код вызывает `Delete` для удаления сотой строки набора строк.

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Delete the row
HRESULT hr = product.Delete();
```

## <a name="immediate-and-deferred-updates"></a>Немедленные и отложенные обновления

Если не указано обратное, вызовы методов `SetData`, `Insert` и `Delete` обновляют хранилище данных немедленно. Вы можете отложить обновления, чтобы клиент сохранил все изменения в локальном кэше, а затем переместил их в хранилище данных при вызове одного из следующих методов обновления.

- [CRowset::Update](../../data/oledb/crowset-update.md) перемещает все ожидающие изменения, внесенные в текущую строку с последнего получения или вызова `Update`.

- [CRowset::UpdateAll](../../data/oledb/crowset-updateall.md) перемещает все ожидающие изменения, внесенные во все строки с момента последнего получения или вызова `Update`.

Обновление в контексте методов обновления относится только к внесению изменений по команде и не должно смешиваться с командой SQL **UPDATE** (`SetData` эквивалентна команде SQL **UPDATE**).

Отложенные обновления нужны, например, в случаях выполнения серии банковских транзакций. Если одна транзакция будет отменена, вы можете отменить изменение, так как вы не отправляете эту серию изменений, пока последнее из них не будет зафиксировано. Также поставщик может объединить изменения в один вызов по сети, что более эффективно.

Для поддержки отложенных изменений необходимо задать свойство `DBPROP_IRowsetChange` в дополнение к свойствам, описанным в разделе **Поддержка операций обновления**.

```cpp
pPropSet->AddProperty(DBPROP_IRowsetUpdate, true);
```

При вызове `Update` или `UpdateAll` эти методы перемещают изменения из локального кэша в хранилище данных, а затем очищают локальный кэш. Так как обновление перемещает изменения только для текущей строки, важно, чтобы приложение отслеживало, какие строки следует обновлять и когда. В следующем примере показано, как обновить две последовательные строки.

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Change the values of columns "Name" and "Units in Stock" in the 100th row of the Product table
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Wick" ) );

product.m_UnitsInStock = 10000;

HRESULT hr = product.SetData();  // No changes made to row 100 yet
product.Update();                 // Update row 100 now

// Change the values of columns "Name" and "Units in Stock" in the 101st row of the Product table
product.MoveNext();

_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName _T( "Wax" ) );

product.m_UnitsInStock = 500;

HRESULT hr = product.SetData();  // No changes made to row 101 yet
product.Update();                 // Update row 101 now
```

Чтобы убедиться, что ожидающие изменения перемещены, перед переходом в другую строку следует вызвать `Update`. Однако если это неэффективно, например когда приложению требуется обновлять сотни строк, вы можете использовать `UpdateAll` для одновременного обновления всех строк.

Например, если бы первый вызов `Update` отсутствовал в коде выше, строка 100 осталась бы без изменений, тогда как строка 101 была бы изменена. После этого вашему приложению потребовалось бы вызвать `UpdateAll` или вернуться к строке 100 и вызвать `Update` для обновления этой строки.

Наконец, основная причина откладывания изменений, — возможность отменить их. Вызов [CRowset::Undo](../../data/oledb/crowset-undo.md) откатывает состояние локального кэша изменений до состояния хранилища данных перед внесением ожидающих изменений. Обратите внимание, что команда `Undo` не откатывает состояние локального кэша на один шаг (до состояния перед последним изменением). Вместо этого она очищает локальный кэш для этой строки. Также команда `Undo` затрагивает только текущую строку.

## <a name="see-also"></a>См. также раздел

[Работа с шаблонами потребителей OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)<br/>
[Класс CRowset](../../data/oledb/crowset-class.md)<br/>
[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))<br/>
