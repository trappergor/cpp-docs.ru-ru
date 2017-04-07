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
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 4a82f66f0b6f6535de8e9707c2d68b94b7eb69c5
ms.lasthandoff: 03/31/2017

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
|[CDBException::m_nRetCode](#m_nretcode)|Содержит код возврата для Open Database Connectivity (ODBC), типа **RETCODE**.|  
|[CDBException::m_strError](#m_strerror)|Содержит строку с описанием ошибки в терминах буквенно-цифровых.|  
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|Содержит строку с описанием ошибки с точки зрения коды ошибок, возвращенный ODBC.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс включает два открытые члены данных, используемого для определения причины возникновения исключения или отобразить текстовое сообщение, описывающее исключение. `CDBException`объекты конструирования и создаваемые функции-члены классов базы данных.  
  
> [!NOTE]
>  Этот класс является одним из классов MFC Open Database Connectivity (ODBC). Если вместо этого используются новые классы объектов доступа к данным (DAO), используйте [CDaoException](../../mfc/reference/cdaoexception-class.md) вместо него. Все имена классов DAO иметь префикс «CDao». Дополнительные сведения см. в статье [Обзор: программирования баз данных](../../data/data-access-programming-mfc-atl.md).  
  
 Исключения случаях чрезмерных выполнения, включающих условия вне элемента управления программы, такие как источник данных или сетевые ошибки ввода-вывода. Ошибки, которые могут ожидать во время обычной выполнения программы, обычно не считаются исключения.  
  
 Эти объекты в области доступны **ПЕРЕХВАТЫВАТЬ** выражение. Можно также создавать `CDBException` объектов из кода с `AfxThrowDBException` глобальной функции.  
  
 Дополнительные сведения об обработке исключений в общие или о `CDBException` объектов, см. в статьях [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md) и [исключений: исключения базы данных](../../mfc/exceptions-database-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdb.h  
  
##  <a name="m_nretcode"></a>CDBException::m_nRetCode  
 Содержит код ошибки ODBC типа **RETCODE** возвращенных функции API-интерфейса программирования приложений ODBC.  
  
### <a name="remarks"></a>Примечания  
 Этот тип включает префикс SQL коды определенном ODBC и префиксом AFX_SQL определяются классами базы данных. Для `CDBException`, этот член будет содержать одно из следующих значений:  
  
- **AFX_SQL_ERROR_API_CONFORMANCE** драйвер `CDatabase::OpenEx` или `CDatabase::Open` вызова не соответствует требуемой согласованности API ODBC 1 ( **SQL_OAC_LEVEL1**).  
  
- **AFX_SQL_ERROR_CONNECT_FAIL** не удалось установить соединение с источником данных. Можно передать **NULL** `CDatabase` указатель на ваш конструктор набора записей и повторная попытка создать подключение на основе `GetDefaultConnect` сбой.  
  
- **AFX_SQL_ERROR_DATA_TRUNCATED** запрошенный больше данных, чем указано хранилище для. Сведения о хранилище данных для увеличения `CString` или `CByteArray` типов данных в разделе `nMaxLength` аргумент для [RFX_Text](record-field-exchange-functions.md#rfx_text) и [RFX_Binary](record-field-exchange-functions.md#rfx_binary) в разделе «Макросы и глобальные переменные».  
  
- **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED** вызов `CRecordset::Open` запрашивающего динамическим подмножеством данных не удалось. Динамические наборы не поддерживаются драйвером.  
  
- **AFX_SQL_ERROR_EMPTY_COLUMN_LIST** предпринята попытка открыть таблицу (или Вы дали невозможно идентифицировать как вызов процедуры или **ВЫБЕРИТЕ** инструкции), но нет столбцов, указанных в поле записи вызовов функции обмена (полями записей RFX) в вашей `DoFieldExchange` переопределения.  
  
- **AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH** тип функции RFX в вашей `DoFieldExchange` переопределение не совместим с типом данных столбца в наборе записей.  
  
- **AFX_SQL_ERROR_ILLEGAL_MODE** Вы вызвали `CRecordset::Update` без предварительного вызова метода `CRecordset::AddNew` или `CRecordset::Edit`.  
  
- **AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED** не удалось выполнить ваш запрос на блокировку записи для обновления, так как драйвер ODBC не поддерживает блокировку.  
  
- **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED** Вы вызвали `CRecordset::Update` или **удалить** не уникальный ключ в таблице и изменить несколько записей.  
  
- **AFX_SQL_ERROR_NO_CURRENT_RECORD** предпринята попытка изменить или удалить ранее запись. Нужно прокручивать экран новой текущей записи после удаления.  
  
- **AFX_SQL_ERROR_NO_POSITIONED_UPDATES** запрос для подмножества не может быть выполнен, поскольку драйвер ODBC не поддерживает позиционированные обновления.  
  
- **AFX_SQL_ERROR_NO_ROWS_AFFECTED** Вы вызвали `CRecordset::Update` или **удалить**, но во время начала операции записи не найден.  
  
- **AFX_SQL_ERROR_ODBC_LOAD_FAILED** попытка загрузки ODBC. Не удалось выполнить DLL; Windows не удалось найти или не удалось загрузить эту библиотеку DLL. Эта ошибка является неустранимой.  
  
- **AFX_SQL_ERROR_ODBC_V2_REQUIRED** не удалось выполнить ваш запрос на динамический набор из-за уровня 2-совместимый драйвер ODBC является обязательным.  
  
- **AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY** попытка прокрутки не удалась, поскольку источник данных не поддерживает обратной прокрутки.  
  
- **AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED** вызов `CRecordset::Open` запрос моментального снимка не удалось. Моментальные снимки не поддерживаются драйвером. (Это должно происходить только при ODBCCURS библиотека курсоров ODBC. Библиотеки DLL, но отсутствует.)  
  
- **AFX_SQL_ERROR_SQL_CONFORMANCE** драйвер `CDatabase::OpenEx` или `CDatabase::Open` вызова не соответствует требуемой согласованности ODBC SQL «Минимум» ( **SQL_OSC_MINIMUM**).  
  
- **AFX_SQL_ERROR_SQL_NO_TOTAL** драйвер ODBC не удалось задать общий размер `CLongBinary` значение данных. Так как не удается предварительно выделенной блока глобальной памяти, возможно, сбой операции.  
  
- **AFX_SQL_ERROR_RECORDSET_READONLY** предпринята попытка обновить набор записей доступным только для чтения или источника данных доступен только для чтения. С набором данных могут быть выполнены никакие операции обновления или `CDatabase` объекта, связанного с ним.  
  
- **Значение SQL_ERROR** функции не удалось. Функция ODBC возвращает сообщение об ошибке **SQLError** хранится в **m_strError** члена данных.  
  
- **SQL_INVALID_HANDLE** сбой функции из-за дескриптора среды недопустимый дескриптора соединения и дескриптора инструкции. Это указывает на программную ошибку. Дополнительные сведения недоступны из функции ODBC **SQLError**.  
  
 Коды с префиксом SQL определяются ODBC. Коды с префиксом AFX определены в файле AFXDB. Символ «H» в MFC\INCLUDE.  
  
##  <a name="m_strerror"></a>CDBException::m_strError  
 Содержит строку с описанием ошибки, вызвавшей исключение.  
  
### <a name="remarks"></a>Примечания  
 Строка описывает ошибку в терминах буквенно-цифровых. Дополнительные сведения и пример см. в разделе **m_strStateNativeOrigin**.  
  
##  <a name="m_strstatenativeorigin"></a>CDBException::m_strStateNativeOrigin  
 Содержит строку с описанием ошибки, вызвавшей исключение.  
  
### <a name="remarks"></a>Примечания  
 Строка имеет форму «состояние: % s, машинный код: % ld, источник: % s», где коды формата, в порядке, заменяются значения, описывающие:  
  
-   **SQLSTATE**, символом null строку, содержащую с кодом ошибки пяти символов, возвращаемых в *szSqlState* параметр функции ODBC **SQLError**. **SQLSTATE** значения перечислены в приложении А [коды ошибок ODBC](https://msdn.microsoft.com/library/ms714687.aspx)в *справочнике программиста ODBC*. Пример: «S0022».  
  
-   Машинный код ошибки, относящиеся к источнику данных, возвращаемых в *pfNativeError* параметр **SQLError** функции. Пример: 207.  
  
-   Текст сообщения об ошибке возвращаются в *szErrorMsg* параметр **SQLError** функции. Это сообщение состоит из нескольких имен в квадратных скобках. При передаче ошибки из источника для пользователя, каждый компонент ODBC (источник данных, драйвер, диспетчер драйверов) добавляет собственное имя. Эта информация помогает выявить источник ошибки. Пример: [Microsoft] [драйвер ODBC для SQL Server] [SQL Server]  
  
 Платформа интерпретирует строку ошибки и помещает его компонентов в **m_strStateNativeOrigin**; Если **m_strStateNativeOrigin** содержит сведения для более одной ошибки ошибки разделяются символы новой строки. Платформа помещает текст буквенно-цифровые ошибки в **m_strError**.  
  
 Дополнительные сведения о кодах, используемых для данной строки см. в разделе [SQLError](https://msdn.microsoft.com/library/ms716312.aspx) функционировать в *справочнике программиста ODBC*.  
  
### <a name="example"></a>Пример  
  Из ODBC: «Состояние: S0022, собственный: 207, источник: [Microsoft] [драйвер ODBC для SQL Server] [SQL Server] недопустимое имя столбца «ColName»»  
  
 В **m_strStateNativeOrigin**: «состояние: S0022, собственный: 207, источник: [Microsoft] [драйвер ODBC для SQL Server] [SQL Server]»  
  
 В **m_strError**: «Недопустимое имя столбца «ColName»»  
  
## <a name="see-also"></a>См. также  
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDatabase-класс](../../mfc/reference/cdatabase-class.md)   
 [CRecordset-класс](../../mfc/reference/crecordset-class.md)   
 [Класс разделе](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::Update](../../mfc/reference/crecordset-class.md#update)   
 [CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)   
 [Класс CException](../../mfc/reference/cexception-class.md)

