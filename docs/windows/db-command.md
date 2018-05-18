---
title: db_command | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.db_command
dev_langs:
- C++
helpviewer_keywords:
- db_command attribute
ms.assetid: 714c3e15-85d7-408b-9a7c-88505c3e5d24
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e0fe3f712566345bb069b798207cfdb10a0aa636
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="dbcommand"></a>db_command
Создает команду OLE DB.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ db_command(   
   command,   
   name,   
   source_name,   
   hresult,   
   bindings,   
   bulk_fetch)  
]  
```  
  
#### <a name="parameters"></a>Параметры  
 `command`  
 Строка команды, содержащая текст команды OLE DB. Ниже приведен простой пример:  
  
```  
[ db_command ( command = "Select * from Products" ) ]  
```  
  
 Синтаксис *команды* выглядит следующим образом:  
  
```  
binding parameter block 1  
   OLE DB command  
binding parameter block 2  
   continuation of OLE DB command  
binding parameter block 3  
...  
```  
  
 *Блок параметров привязки* определяется следующим образом:  
  
 **([** `bindtype` **]** *szVar1* [*, szVar2* [, *nVar3* [, ...]]] **)**  
  
 Здесь:  
  
 **(** отмечает начало блока привязки данных.  
  
 **[** `bindtype` **]** является одной из следующих строк без учета регистра:  
  
-   **[db_column]** привязывает каждую из переменных-членов к столбцу в наборе строк.  
  
-   **[bindto]** (то же, что и **[db_column]**).  
  
-   **[in]** привязывает переменные-члены в качестве входных параметров.  
  
-   **[out]** привязывает переменные-члены в качестве выходных параметров.  
  
-   **[in,out]** привязывает переменные-члены в качестве входных и выходных параметров.  
  
 *SzVarX* разрешается в переменную-член в рамках текущей области.  
  
 **)** отмечает конец блока привязки данных.  
  
 Если строка команды содержит один или несколько описателей, таких как [in], [out] или [in/out], **db_command** формирует карту параметров.  
  
 Если строка команды содержит один или более параметров, таких как [db_column] или [bindto] **db_command** создает набор строк и карту метода доступа для обслуживания этих связанных переменных. Дополнительные сведения см. в описании [db_accessor](../windows/db-accessor.md) .  
  
> [!NOTE]
>  Синтаксис [`bindtype`] и параметр `bindings` не действуют при использовании **db_command** на уровне класса.  
  
 Ниже приведены некоторые примеры привязки блоков параметров. Следующий пример привязывает элементы данных `m_au_fname` и `m_au_lname` соответственно к столбцам `au_fname` и `au_lname` , из таблицы authors базы данных pubs:  
  
```  
TCHAR m_au_fname[21];  
TCHAR m_au_lname[41];  
TCHAR m_state[3] = 'CA';  
  
[db_command (  
   command = "SELECT au_fname([bindto]m_au_fname), au_lname([bindto]m_au_lname) " \  
   "FROM dbo.authors " \  
   "WHERE state = ?([in]m_state)")  
```  
  
 ]  
  
 *name* (необязательно)  
 Имя дескриптора, используемого для работы с набором строк. При указании *name* **db_command** создает класс с указанным *именем*, который можно использовать для просмотра набора строк или для выполнения нескольких запросов на изменение. Если не указать *name*, пользователю нельзя будет вернуть больше одной строки результатов.  
  
 *source_name* (необязательно)  
 Переменная `CSession` или экземпляр класса с примененным атрибутом `db_source` , по которому выполняется команда. См. описание [db_source](../windows/db-source.md).  
  
 **db_command** проверяет допустимость переменной, используемой для *source_name* , поэтому указанная переменная должна находиться в функции или глобальной области.  
  
 `hresult` (необязательно)  
 Определяет переменную, которая будет получать `HRESULT` этой команды базы данных. Если переменная не существует, она будет автоматически внедрена с помощью атрибута.  
  
 *bindings* (необязательно)  
 Позволяет отделить параметры привязки от команды OLE DB.  
  
 Если указать значение для `bindings`, **db_command** проанализирует сопоставленное значение и не будет анализировать параметр [`bindtype`]. Это позволяет использовать синтаксис поставщика OLE DB. Чтобы отключить синтаксический анализ без параметров привязки, укажите **Bindings=""**.  
  
 Если не указать значение для `bindings`, **db_command** будет анализировать блок параметров привязки, выполняя поиск "**(**", за которым следует **[**`bindtype`**]** в квадратных скобках, одна или несколько ранее объявленных переменных-членов C++ и затем "**)**". Весь текст в скобках будет убран из итоговой команды, и эти параметры будут использоваться для создания привязок параметров и столбцов для этой команды.  
  
 *bulk_fetch*(необязательно)  
 Целое число, указывающее число получаемых строк.  
  
 Значение по умолчанию 1 обозначает получение одной строки (набор строк будет иметь тип [CRowset](../data/oledb/crowset-class.md)).  
  
 Значение больше 1 обозначает массовое получение строк. Массовое получение строк относится к возможности большого набора строк получить несколько дескрипторов строк (набор строк будет иметь тип [CBulkRowset](../data/oledb/cbulkrowset-class.md) и вызывать `SetRows` с указанным числом строк).  
  
 Если *bulk_fetch* меньше единицы, `SetRows` возвращает нуль.  
  
## <a name="remarks"></a>Примечания  
 **db_command** создает объект [CCommand](../data/oledb/ccommand-class.md) , который используется потребителем OLE DB для выполнения команды.  
  
 Можно использовать **db_command** с областью класса или функции; основное различие заключается в области объекта `CCommand` . В области видимости функции такие данные, как привязки, завершаются в конце функции. Использования области видимости класса и функции включают класс шаблон потребителя OLE DB **CCommand <>**, но отличаются аргументов шаблона для случаев, функций и классов. В случае функции привязки выполняются для **метода доступа** , который содержит локальные переменные, а в случае с классом в качестве аргумента определяется класс, производный от `CAccessor`. При использовании в качестве атрибута класса **db_command** работает в сочетании с **db_column**.  
  
 **db_command** можно использовать для выполнения команд, которые не возвращают результирующий набор.  
  
 Когда поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор будет Переименуйте класс в \_ *имя_класса*метод доступа, где *имя_класса* является названием также создайте класс с именем класса и компилятор *имя_класса*, который является производным от \_ *имя_класса*метода доступа.  В представлении классов отображаются оба класса.  
  
## <a name="example"></a>Пример  
 Этот образец определяет команду, которая выбирает первое и последнее имена из таблицы, в которой столбец состояния соответствует значению "CA". **db_command** создает и считывает набор строк, для которого можно вызывать создаваемые мастером функции, например [OpenAll и CloseAll](../data/oledb/consumer-wizard-generated-methods.md), а также функции-члены `CRowset` , такие как [MoveNext](../data/oledb/crowset-movenext.md).  
  
 Обратите внимание, что в этом коде вам требуется предоставить собственную строку подключения, которая подключается к базе данных pubs. Сведения о том, как это сделать в среде разработки, см. в разделах [How to: Connect to a Database from Server Explorer](http://msdn.microsoft.com/en-us/7c1c3067-0d77-471b-872b-639f9f50db74) и [How to: Add New Data Connections in Server Explorer/Database Explorer](http://msdn.microsoft.com/en-us/fb2f513b-ddad-4142-911e-856bba0054c8).  
  
```  
// db_command.h  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
#pragma once  
  
[  db_source(L"your connection string"),  
   db_command(L" \  
      SELECT au_lname, au_fname \  
      FROM dbo.authors \  
      WHERE state = 'CA'")  ]  
  
struct CAuthors {  
   // In order to fix several issues with some providers, the code below may bind  
   // columns in a different order than reported by the provider  
  
   DBSTATUS m_dwau_lnameStatus;  
   DBSTATUS m_dwau_fnameStatus;  
   DBLENGTH m_dwau_lnameLength;  
   DBLENGTH m_dwau_fnameLength;  
  
   [ db_column("au_lname", status="m_dwau_lnameStatus", length="m_dwau_lnameLength") ] TCHAR m_au_lname[41];  
   [ db_column("au_fname", status="m_dwau_fnameStatus", length="m_dwau_fnameLength") ] TCHAR m_au_fname[21];  
  
   [ db_param("7", paramtype="DBPARAMIO_INPUT") ] TCHAR m_state[3];  
  
   void GetRowsetProperties(CDBPropSet* pPropSet) {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   }  
};  
```  
  
## <a name="example"></a>Пример  
  
```  
// db_command.cpp  
// compile with: /c  
#include "db_command.h"  
  
int main(int argc, _TCHAR* argv[]) {  
   HRESULT hr = CoInitialize(NULL);  
  
   // Instantiate rowset  
   CAuthors rs;  
  
   // Open rowset and move to first row  
   strcpy_s(rs.m_state, sizeof(rs.m_state), _T("CA"));  
   hr = rs.OpenAll();  
   hr = rs.MoveFirst();  
  
   // Iterate through the rowset  
   while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET ) {  
      // Print out the column information for each row  
      printf("First Name: %s, Last Name: %s\n", rs.m_au_fname, rs.m_au_lname);  
      hr = rs.MoveNext();  
   }  
  
   rs.CloseAll();  
   CoUninitialize();  
}  
```  
  
## <a name="example"></a>Пример  
 В этом примере используется `db_source` для класса источника данных `CMySource`, и `db_command` для классов команд `CCommand1` и `CCommand2`.  
  
```  
// db_command_2.cpp  
// compile with: /c  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
// class usage for both db_source and db_command  
  
[  db_source(L"your connection string"),  
   db_command(L" \  
      SELECT au_lname, au_fname \  
      FROM dbo.authors \  
      WHERE state = 'CA'")  ]  
struct CMySource {  
   HRESULT OpenDataSource() {  
      return S_OK;  
   }  
};  
  
[db_command(command = "SELECT * FROM Products")]  
class CCommand1 {};  
  
[db_command(command = "SELECT FNAME, LNAME FROM Customers")]  
class CCommand2 {};  
  
int main() {  
   CMySource s;  
   HRESULT hr = s.OpenDataSource();  
   if (SUCCEEDED(hr)) {  
      CCommand1 c1;  
      hr = c1.Open(s);  
  
      CCommand2 c2;  
      hr = c2.Open(s);  
   }  
  
   s.CloseDataSource();  
}  
```  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**class**, `struct`, member, method, local|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты потребителя OLE DB](../windows/ole-db-consumer-attributes.md)   
 [Изолированные атрибуты](../windows/stand-alone-attributes.md)   
