---
title: Методы, создаваемые мастером объекта-получателя
ms.date: 11/04/2016
helpviewer_keywords:
- OpenAll method
- attribute-injected classes and methods
- wizard-generated classes and methods
- OLE DB consumers, wizard-generated classes and methods
- methods [C++], OLE DB Consumer Wizard-generated
- CloseDataSource method
- consumer wizard-generated classes and methods
- OpenDataSource method
- CloseAll method
- OpenRowset method
- GetRowsetProperties method
ms.assetid: d80ee51c-8bb3-4dca-8760-5808e0fb47b4
ms.openlocfilehash: d525c0e82d7fbc8bf0f83217eaa2cf9a1bd2f17b
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331858"
---
# <a name="consumer-wizard-generated-methods"></a>Методы, создаваемые мастером объекта-получателя

**Мастер потребителя ATL OLE DB** и **мастер приложений MFC** создают определенные функции, которые следует иметь в виду. Некоторые методы реализуются по-разному в проектах с атрибутами, поэтому существует несколько моментов; Ниже описаны все случаи. Сведения о просмотре внедренного кода см. в разделе [Отладка внедренного кода](/visualstudio/debugger/how-to-debug-injected-code).

- `OpenAll` Открывает источник данных, наборы строк и включает закладки, если они доступны.

- `CloseAll` Закрывает все открытые наборы строк и прекращает выполнение всех команд.

- `OpenRowset` вызывается `OpenAll` для открытия набора строк потребителя или наборы строк.

- `GetRowsetProperties` Извлекает указатель на свойство в наборе строк с помощью свойства, которые могут быть заданы.

- `OpenDataSource` Открывает источник данных, используя указанный в строке инициализации **свойства канала передачи данных** диалоговое окно.

- `CloseDataSource` закрывает источник данных соответствующим образом.

## <a name="openall-and-closeall"></a>OpenAll и CloseAll

```cpp
HRESULT OpenAll();

void CloseAll();
```

В следующем примере показано, как можно вызвать `OpenAll` и `CloseAll` при выполнении той же команды несколько раз. Сравните пример кода в [CCommand::Close](../../data/oledb/ccommand-close.md), который показан вариант, который вызывает `Close` и `ReleaseCommand` вместо `CloseAll`.

```cpp
int main(int argc, char* argv[])
{
   HRESULT hr;

   hr = CoInitialize(NULL);

   CCustOrdersDetail rs;      // Your CCommand-derived class
   rs.m_OrderID = 10248;      // Open order 10248
   hr = rs.OpenAll();         // (Open also executes the command)
   hr = rs.MoveFirst();         // Move to the first row and print it
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );

   // Close the first command execution
   rs.Close();

   rs.m_OrderID = 10249;      // Open order 10249 (a new order)
   hr = rs.Open();            // (Open also executes the command)
   hr = rs.MoveFirst();         // Move to the first row and print it
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );

   // Close the second command execution;
   // Instead of rs.CloseAll() you could call
   // rs.Close() and rs.ReleaseCommand():
   rs.CloseAll();

   CoUninitialize();
   return 0;
}
```

### <a name="remarks"></a>Примечания

Если вы определяете `HasBookmark` метод, `OpenAll` кода задается `DBPROP_IRowsetLocate` свойство; убедитесь, что только в том случае, если используемый поставщик поддерживает это свойство.

## <a name="openrowset"></a>OpenRowset

```cpp
// OLE DB Template version:
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)
// Attribute-injected version:
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);
```

`OpenAll` вызывает этот метод для открытия набора или наборов строк в объекте-получателе. Как правило, не нужно вызывать `OpenRowset` только если вы хотите работать с несколькими источниками данных и сеансы либо/строк. `OpenRowset` объявляется в файле заголовка класса команд или таблиц:

```cpp
// OLE DB Template version:
HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)
{
   HRESULT hr = Open(m_session, NULL, pPropSet);
   #ifdef _DEBUG
   if(FAILED(hr))
      AtlTraceErrorRecords(hr);
   #endif
   return hr;
}
```

Атрибуты реализуют этот метод по-разному. Эта версия принимает объект сеанса и командной строки, который по умолчанию для командной строки, указанной в db_command, несмотря на то, что вы можете передать его. Если вы определяете `HasBookmark` метод, `OpenRowset` кода задается `DBPROP_IRowsetLocate` свойство; убедитесь, что только в том случае, если используемый поставщик поддерживает это свойство.

```cpp
// Attribute-injected version:
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand=NULL)
{

   DBPROPSET *pPropSet = NULL;
   CDBPropSet propset(DBPROPSET_ROWSET);
   __if_exists(HasBookmark)

   {
      propset.AddProperty(DBPROP_IRowsetLocate, true);
      pPropSet= &propset;
      }
...
}
```

## <a name="getrowsetproperties"></a>GetRowsetProperties

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet);
```

Этот метод извлекает указатель на набор свойств набора строк; Этот указатель можно использовать для задания свойств, таких как `DBPROP_IRowsetChange`. `GetRowsetProperties` используется в класс записей пользователя следующим образом. Можно изменить этот код, чтобы задать дополнительные свойства набора строк:

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet)
{
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
}
```

### <a name="remarks"></a>Примечания

Не следует определять глобальный `GetRowsetProperties` метод, так как он может конфликтовать с одним определен с помощью мастера. Это созданный мастером метод, который вы получаете с атрибутами и шаблонного проектов; Эти атрибуты не внедряют этот код.

## <a name="opendatasource-and-closedatasource"></a>OpenDataSource и CloseDataSource

```cpp
HRESULT OpenDataSource();

void CloseDataSource();
```

### <a name="remarks"></a>Примечания

Мастер определяет методы `OpenDataSource` и `CloseDataSource`; `OpenDataSource` вызовы [CDataSource::OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md).

## <a name="see-also"></a>См. также

[Создание объекта-получателя OLE DB с помощью мастера](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)