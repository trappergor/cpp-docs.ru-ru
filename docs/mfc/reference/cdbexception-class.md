---
title: "Класс CDBException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBException
dev_langs:
- C++
helpviewer_keywords:
- CDBException class
- exceptions [C++], database
- database exceptions [C++]
- ODBC classes [C++], exceptions
- errors [C++], database
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fc3bf7be273bf509dd1ee79fb42e69050070e830
ms.lasthandoff: 02/24/2017

---
# <a name="cdbexception-class"></a>Класс CDBException
Представляет условие исключения, поступающее от классов базы данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CDBException : public CException  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDBException::m_nRetCode](#m_nretcode)|Содержит код возврата Open Database Connectivity (ODBC), типа **RETCODE**.|  
|[CDBException::m_strError](#m_strerror)|Содержит строку с описанием ошибки в терминах буквенно-цифровых.|  
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|Содержит строку, описывающую ошибку с точки зрения коды ошибок ODBC.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс включает две открытые члены данных, используемого для определения причины исключения и отображать текстовое сообщение, описывающее исключение. `CDBException`объекты конструирования и создаваемые функции-члены классов базы данных.  
  
> [!NOTE]
>  Этот класс является одним из классов MFC Open Database Connectivity (ODBC). Если вместо этого используются новые классы объектов доступа к данным (DAO), используйте [CDaoException](../../mfc/reference/cdaoexception-class.md) вместо. Все имена классов DAO имеют «CDao» как префикс. Дополнительные сведения см. в статье [Обзор: программирования баз данных](../../data/data-access-programming-mfc-atl.md).  
  
 Исключения случаях чрезмерное выполнения, включающие условия за пределами элемента управления программы, такие как источник данных или сетевых операций ввода-вывода ошибок. Ошибки, которые могут ожидать при типичном ходе выполнения программы, обычно не считаются исключения.  
  
 Можно использовать эти объекты в области **CATCH** выражение. Можно также создавать `CDBException` объектов из кода с помощью `AfxThrowDBException` глобальной функции.  
  
 Дополнительные сведения об обработке исключений в общие или о `CDBException` объектов, см. в статьях [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md) и [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  
##  <a name="a-namemnretcodea--cdbexceptionmnretcode"></a><a name="m_nretcode"></a>CDBException::m_nRetCode  
 Содержит код ошибки ODBC типа **RETCODE** возвращенный функции API-интерфейс программирования приложений ODBC.  
  
### <a name="remarks"></a>Примечания  
 Этот тип включает префикс SQL коды определяется ODBC и префиксом AFX_SQL определенные классы баз данных. Для `CDBException`, этот элемент будет содержать одно из следующих значений:  
  
- **AFX_SQL_ERROR_API_CONFORMANCE** драйвер `CDatabase::OpenEx` или `CDatabase::Open` вызова не соответствует требуемой согласованности API ODBC 1 ( **SQL_OAC_LEVEL1**).  
  
- **AFX_SQL_ERROR_CONNECT_FAIL** не удалось установить соединение с источником данных. Можно передать **NULL** `CDatabase` указатель на конструктор набора записей и последующие попытки создания подключения на основе `GetDefaultConnect` сбой.  
  
- **AFX_SQL_ERROR_DATA_TRUNCATED** вы запросили больше данных, чем вы предоставили хранилища для. Сведения о хранилище данных для увеличения `CString` или `CByteArray` типы данных в разделе `nMaxLength` аргумент для [RFX_Text](http://msdn.microsoft.com/library/de3c7581-d26c-40cb-81f3-c492ef4809f6) и [RFX_Binary](http://msdn.microsoft.com/library/908ff945-3ad0-43a1-9932-cdcdc8b14915) в разделе «Макросы и глобальные объекты».  
  
- **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED** вызов `CRecordset::Open` запрос подмножества сбой. Динамические наборы не поддерживаются драйвером.  
  
- **AFX_SQL_ERROR_EMPTY_COLUMN_LIST** попытка открыть таблицу (или вы присвоили невозможно идентифицировать как вызов процедуры или **ВЫБЕРИТЕ** инструкции), но нет столбцов, определенных в вызовах функций обмена (полями записей RFX) поле записи в вашей `DoFieldExchange` переопределить.  
  
- **AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH** тип функции RFX в вашей `DoFieldExchange` переопределение не совместим с типом данных столбца в наборе записей.  
  
- **AFX_SQL_ERROR_ILLEGAL_MODE** именем `CRecordset::Update` без вызова ранее `CRecordset::AddNew` или `CRecordset::Edit`.  
  
- **AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED** не удалось выполнить ваш запрос на блокировку записи для обновления, так как драйвер ODBC не поддерживает блокировку.  
  
- **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED** именем `CRecordset::Update` или **удаление** для таблицы с уникальным ключом и изменить несколько записей.  
  
- **AFX_SQL_ERROR_NO_CURRENT_RECORD** предпринята попытка изменить или удалить ранее запись. Нужно прокручивать экран новой текущей записи после удаления.  
  
- **AFX_SQL_ERROR_NO_POSITIONED_UPDATES** запрос для подмножества не удалось выполнить, поскольку драйвер ODBC не поддерживает позиционированные обновления.  
  
- **AFX_SQL_ERROR_NO_ROWS_AFFECTED** именем `CRecordset::Update` или **удаление**, но начала операции больше не будет найдена запись.  
  
- **AFX_SQL_ERROR_ODBC_LOAD_FAILED** попытка загрузки ODBC. Сбой библиотеки DLL; Windows не удалось найти или не удалось загрузить этот DLL. Эта ошибка является неустранимой.  
  
- **AFX_SQL_ERROR_ODBC_V2_REQUIRED** не удалось выполнить запрос подмножества, так как требуется уровня 2-совместимый драйвер ODBC.  
  
- **AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY** попытка прокрутки не выполнена, поскольку источник данных не поддерживает обратной прокрутки.  
  
- **AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED** вызов `CRecordset::Open` запросе моментального снимка не удалось. Моментальные снимки не поддерживаются драйвером. (Это должно происходить только если библиотека курсоров ODBC â €» ODBCCURS. DLL â €» не существует).  
  
- **AFX_SQL_ERROR_SQL_CONFORMANCE** драйвер `CDatabase::OpenEx` или `CDatabase::Open` вызова не соответствует требуемой согласованности ODBC SQL «Минимум» ( **SQL_OSC_MINIMUM**).  
  
- **AFX_SQL_ERROR_SQL_NO_TOTAL** драйвер ODBC не удалось задать общий размер `CLongBinary` значение данных. Так как не быть предварительно блока глобальной памяти, возможно, сбой операции.  
  
- **AFX_SQL_ERROR_RECORDSET_READONLY** предпринята попытка обновить набор записей доступным только для чтения или источника данных доступен только для чтения. Операции обновления не могут быть выполнены с набора записей или `CDatabase` объекта, связанного с ним.  
  
- **Значение SQL_ERROR** сбой функции. Сообщение об ошибке, возвращаемое функцией ODBC **SQLError** хранится в **m_strError** данные-член.  
  
- **SQL_INVALID_HANDLE** сбой функции из-за дескриптора недопустимый среды, дескриптор подключения или дескриптор инструкции. Это указывает на программную ошибку. Дополнительные сведения недоступны из функции ODBC **SQLError**.  
  
 Коды префиксом SQL определены в ODBC. Коды префиксом AFX определены в файле AFXDB. H в MFC\INCLUDE.  
  
##  <a name="a-namemstrerrora--cdbexceptionmstrerror"></a><a name="m_strerror"></a>CDBException::m_strError  
 Содержит строку, описывающую ошибку, вызвавшую исключение.  
  
### <a name="remarks"></a>Примечания  
 Строка описывает ошибку в терминах буквенно-цифровых. Более подробные сведения и пример см. в разделе **m_strStateNativeOrigin**.  
  
##  <a name="a-namemstrstatenativeorigina--cdbexceptionmstrstatenativeorigin"></a><a name="m_strstatenativeorigin"></a>CDBException::m_strStateNativeOrigin  
 Содержит строку, описывающую ошибку, вызвавшую исключение.  
  
### <a name="remarks"></a>Примечания  
 Строка имеет форму «состояние: % s, машинный код: % ld источника: % s», где коды формата, в порядке, заменяются значениями, которые описывают:  
  
-   **SQLSTATE**, заканчивающаяся нулем строка, содержащая код ошибки пяти символов, возвращаемых в *szSqlState* параметр функции ODBC **SQLError**. **SQLSTATE** значения перечислены в приложении А [коды ошибок ODBC](https://msdn.microsoft.com/library/ms714687.aspx)в *Справочник программиста по ODBC*. Пример: «S0022».  
  
-   Код внутренней ошибки, относящиеся к источнику данных возвращается в *pfNativeError* параметр **SQLError** функции. Пример: 207.  
  
-   Текст сообщения об ошибке возвращаются в *szErrorMsg* параметр **SQLError** функции. Это сообщение состоит из нескольких имен в квадратных скобках. При передаче ошибки из источника для пользователя каждый компонент ODBC (источник данных, драйвер, диспетчер драйверов) добавляет собственное имя. Эта информация помогает выявить источник ошибки. Пример: [Microsoft] [драйвер ODBC сервера SQL] [SQL Server]  
  
 Платформа интерпретирует строку ошибки и помещает его компонентов в **m_strStateNativeOrigin**; Если **m_strStateNativeOrigin** содержит сведения для более одной ошибки, ошибки разделяются символы новой строки. Платформа помещает текст ошибки буквы в **m_strError**.  
  
 Дополнительные сведения о кодах, используемых для этой строки в разделе [SQLError](https://msdn.microsoft.com/library/ms716312.aspx) работать в *Справочник программиста по ODBC*.  
  
### <a name="example"></a>Пример  
  Из ODBC: «Состояние: S0022, машинный код:&207;, источник: [Microsoft] [драйвер ODBC сервера SQL] [SQL Server] недопустимое имя столбца «ColName»»  
  
 В **m_strStateNativeOrigin**: «состояние: S0022, машинный код:&207;, источник: [Microsoft] [драйвер ODBC сервера SQL] [SQL Server]»  
  
 В **m_strError**: «Недопустимое имя столбца «ColName»»  
  
## <a name="see-also"></a>См. также  
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDatabase-класс](../../mfc/reference/cdatabase-class.md)   
 [Класс CRecordset](../../mfc/reference/crecordset-class.md)   
 [Класс разделе](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::Update](../../mfc/reference/crecordset-class.md#update)   
 [CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)   
 [CException-класс](../../mfc/reference/cexception-class.md)

