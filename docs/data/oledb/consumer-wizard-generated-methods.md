---
title: Методы, создаваемые мастером потребителя | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c0e03d24f61b3eba1ff4c6fa1e4d888a0252a21b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098606"
---
# <a name="consumer-wizard-generated-methods"></a>Методы, создаваемые мастером объекта-получателя
Мастер потребителя ATL OLE DB и мастер приложений MFC создают определенные функции, которые следует иметь в виду. Обратите внимание, что по-разному реализованы некоторые методы в проектах с атрибутами предостережений несколько; Ниже описаны все случаи. Сведения о просмотре внедренного кода см. в разделе [Отладка внедренного кода](/visualstudio/debugger/how-to-debug-injected-code).  
  
-   `OpenAll` Открывает источник данных, наборы строк и включает закладки, если они доступны.  
  
-   `CloseAll` Закрывает все открытые наборы строк и прекращает выполнение всех команд.  
  
-   `OpenRowset` вызывается методом OpenAll для открытия набора или наборов строк потребителя.  
  
-   `GetRowsetProperties` Извлекает указатель на значение свойства в наборе строк с которого могут быть заданы свойства.  
  
-   `OpenDataSource` Открывает источник данных, используя заданную в строку инициализации **свойства связи данных** диалоговое окно.  
  
-   `CloseDataSource` закрывает источник данных подходящим способом.  
  
## <a name="openall-and-closeall"></a>OpenAll и CloseAll  
  
```  
HRESULT OpenAll();   

void CloseAll();  
```  
  
 В следующем примере показано, как можно вызвать `OpenAll` и `CloseAll` при повторном выполнении одной команды. Сравните пример кода в [CCommand::Close](../../data/oledb/ccommand-close.md), который демонстрирует вариант вызова **закрыть** и `ReleaseCommand` вместо `CloseAll`.  
  
```  
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
  
## <a name="remarks"></a>Примечания  
 Обратите внимание, что при определении `HasBookmark` метода `OpenAll` код задает свойству DBPROP_IRowsetLocate; убедитесь, что только в том случае, если поставщик поддерживает это свойство.  
  
## <a name="openrowset"></a>Функции OpenRowset  
  
```  
// OLE DB Template version:   
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);  
```  
  
 **OpenAll** вызывает этот метод для открытия набора или наборов строк в объекте-получателе. Как правило, необязательно вызывать `OpenRowset` Если не требуется для работы с несколькими источниками данных и сеансы либо или строк. `OpenRowset` объявляется в файле заголовка класса команд или таблиц.  
  
```  
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
  
 Атрибуты реализуют этот метод по-разному. Эта версия принимает объект сеанса и командной строки, который по умолчанию для командной строки, указанной в db_command, несмотря на то, что вы можете передать его. Обратите внимание, что при определении `HasBookmark` метода `OpenRowset` код задает свойству DBPROP_IRowsetLocate; убедитесь, что только в том случае, если поставщик поддерживает это свойство.  
  
```  
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
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet);  
```  
  
 Этот метод извлекает указатель набора свойств набора строк; Этот указатель можно использовать для задания свойства, такие как DBPROP_IRowsetChange. `GetRowsetProperties` используется в класс записей пользователя следующим образом. Можно изменить этот код, чтобы задать дополнительные свойства набора строк:  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet)  
{  
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
}  
```  
  
## <a name="remarks"></a>Примечания  
 Не следует определять глобальный `GetRowsetProperties` метод, так как он может конфликтовать с каким-либо определенным мастером. Обратите внимание, что созданный мастером метод, который вы получаете с атрибутами и шаблон проектов; атрибуты не вводят данный код.  
  
## <a name="opendatasource-and-closedatasource"></a>Функция OpenDataSource и CloseDataSource  
  
```  
HRESULT OpenDataSource();   

void CloseDataSource();  
```  
  
## <a name="remarks"></a>Примечания  
 Мастер определяет методы, `OpenDataSource` и `CloseDataSource`; `OpenDataSource` вызовы [CDataSource::OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md).  
  
## <a name="see-also"></a>См. также  
 [Создание объекта-получателя OLE DB с помощью мастера](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)