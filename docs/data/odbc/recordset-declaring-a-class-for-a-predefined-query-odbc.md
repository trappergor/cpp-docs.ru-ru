---
title: "Набор записей: Объявление класса для предопределенного запроса (ODBC) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC recordsets, queries
- predefined queries and recordsets
- stored procedures, and recordsets
- recordsets, predefined queries
- recordsets, stored procedures
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8ecdc146610fe20dcc007d6b1223d7108e1ee595
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-declaring-a-class-for-a-predefined-query-odbc"></a>Набор записей. Объявление класса для предопределенного запроса (ODBC)
Этот раздел относится к классам MFC ODBC.  
  
 В этом разделе объясняется, как создать класс набора записей для предопределенного запроса (иногда называется хранимой процедурой, как Microsoft SQL Server).  
  
> [!NOTE]
>  Этот раздел относится к объектам, производным от `CRecordset` в какой строке массовая выборка не был реализован. Если реализована массовая выборка строк, процесс очень похож. Сведения о различиях между наборами записей, выборка строк и те, которые этого не сделать, см. [набор записей: групповая выборка записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Некоторые системы управления базами данных (СУБД) позволяют создавать предопределенные запросы и вызывать его из программ подобно функции. Запрос имеет имя, могут принимать параметры и могут возвращать записи. В этом разделе описано, как для вызова предопределенного запроса, который возвращает записи (и, возможно, имеет параметры).  
  
 Классы баз данных не поддерживают обновление предопределенных запросов. Разница между предопределенного запроса моментального снимка и динамический набор предопределенных запросов не обновляемости, а также изменений, внесенных другими пользователями (или других наборов записей в программе) отображаются в наборе записей.  
  
> [!TIP]
>  Набор записей для вызова предопределенного запроса, который не возвращает записи не обязательно. Подготовка инструкции SQL, как описано ниже, но запускайте его путем вызова `CDatabase` функции-члена [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql).  
  
 Можно создать один класс набора записей для управления вызовом предопределенного запроса, но необходимо выполнить некоторые работу самостоятельно. Мастера не поддерживают создание класса специально для этой цели.  
  
#### <a name="to-create-a-class-for-calling-a-predefined-query-stored-procedure"></a>Создание класса для вызова предопределенного запроса (хранимой процедуры)  
  
1.  Используйте [мастер потребителей ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md) из **добавить класс** для создания класса набора записей для таблицы, содержащей наиболее столбцов, возвращаемых запросом. Это обеспечивает надежную основу.  
  
2.  Вручную добавьте поля элементов данных для всех столбцов всех таблиц, которые возвращаются запросом, но мастер не была создана для вас.  
  
     Например если запрос возвращает три столбца из двух дополнительных таблиц, добавьте к классу шесть элементами данных полей (соответствующих типов данных).  
  
3.  Вручную добавьте [RFX](../../data/odbc/record-field-exchange-rfx.md) вызовы функции [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) функцию-член класса, соответствующий типу данных каждого добавлены элемента данных поля.  
  
    ```  
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:   
    pFX->SetFieldType( CFieldExchange::outputColumn );  
    ```  
  
    > [!NOTE]
    >  Необходимо знать типы данных и порядок столбцов, возвращаемые в результирующий набор. Порядок функции RFX вызывает в `DoFieldExchange` должен соответствовать порядку столбцов результирующего набора.  
  
4.  Вручную добавьте инициализации для новых членов данных поля в конструкторе класса набора записей.  
  
     Также необходимо увеличить значение инициализации для [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) члена данных. Мастер создает инициализацию, но она охватывает только поля элементов данных, добавляемых для вас. Пример:  
  
    ```  
    m_nFields += 6;  
    ```  
  
     Некоторые типы данных не должны инициализироваться здесь, например, `CLongBinary` или массивов байтов.  
  
5.  Если запрос принимает параметры, добавьте элемент данных параметра для каждого параметра, вызов функции RFX для каждого и инициализацию.  
  
6.  Необходимо увеличить `m_nParams` для каждого добавленного параметра, как это было сделано `m_nFields` для добавленных полей в шаге 4 этой процедуры. Дополнительные сведения см. в разделе [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
7.  Вручную записать строку инструкции SQL следующего вида:  
  
    ```  
    {CALL proc-name [(? [, ?]...)]}  
    ```  
  
     где **вызвать** — это ключевое слово ODBC, **proc-name** является имя запроса, как оно записано в источнике данных и «?» — это местозаполнители для значений параметров, указываемое в набор записей во время выполнения (если таковые имеются) . В следующем примере добавляется заполнитель для одного параметра:  
  
    ```  
    CString mySQL = "{CALL Delinquent_Accts (?)}";  
    ```  
  
8.  В коде, который открывает набор записей, задайте значения параметров набора записей элементов данных, а затем вызвать **откройте** функция-член, передав строку SQL **lpszSQL** параметра. Либо замените строку, возвращаемую `GetDefaultSQL` функции-члена в классе.  
  
 В следующих примерах показано процедура вызова предопределенного запроса, с именем `Delinquent_Accts`, который принимает один параметр — номер региона продаж. Этот запрос возвращает три столбца: `Acct_No`, `L_Name`, `Phone`. Все столбцы имеют из таблицы Customers.  
  
 Следующий набор записей определяет члены данных поля для столбцов, возвращаемых запросом и параметр для продажи, Округ — во время выполнения запрошенного числа.  
  
```  
class CDelinquents : public CRecordset  
{  
// Field/Param Data  
    LONG m_lAcct_No;  
    CString m_strL_Name;  
    CString m_strPhone;  
    LONG m_lDistParam;  
    // ...  
};  
```  
  
 Это объявление класса является написанному мастером, за исключением `m_lDistParam` группу добавляется вручную. Другие члены здесь не показаны.  
  
 В следующем примере показаны инициализации для членов данных в `CDelinquents` конструктора.  
  
```  
CDelinquents::CDelinquents(CDatabase* pdb)  
   : CRecordset(pdb)  
{  
    // Wizard-generated params:  
    m_lAcct_No = 0;  
    m_strL_Name = "";  
    m_strPhone = "";  
    m_nFields = 3;  
    // User-defined params:  
    m_nParams = 1;  
    m_lDistParam = 0;  
}  
```  
  
 Обратите внимание, инициализации для [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) и [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams). Мастер инициализирует `m_nFields`; инициализации `m_nParams`.  
  
 В следующем примере показаны функции RFX в `CDelinquents::DoFieldExchange`:  
  
```  
void CDelinquents::DoFieldExchange(CFieldExchange* pFX)  
{  
    pFX->SetFieldType(CFieldExchange::outputColumn);  
    RFX_Long(pFX, "Acct_No", m_lAcct_No);  
    RFX_Text(pFX, "L_Name", m_strL_Name);  
    RFX_Text(pFX, "Phone", m_strPhone);  
    pFX->SetFieldType(CFieldExchange::param);  
    RFX_Long(pFX, "Dist_No", m_lDistParam);  
}  
```  
  
 Помимо того, что вызовы функций RFX для трех возвращаемых столбцов, этот код также управляет привязкой параметра, передаваемого во время выполнения. Параметр подключается к `Dist_No` столбца (номер региона).  
  
 В следующем примере показано, как настроить строку SQL и способ его использования для открытия набора записей.  
  
```  
// Construct a CDelinquents recordset object  
CDelinquents rsDel( NULL );  
CString strSQL = "{CALL Delinquent_Accts (?)}"  
// Specify a parameter value (obtained earlier from the user)  
rsDel.m_lDistParam = lDistrict;  
// Open the recordset and run the query  
if( rsDel.Open( CRecordset::snapshot, strSQL ) )  
    // Use the recordset ...  
```  
  
 Этот код создает моментальный снимок, передает ему параметр, полученный ранее от пользователя и вызывает предопределенный запрос. При выполнении запроса возвращаются записи для указанного региона продаж. Каждая запись содержит столбцы для номера счета, Фамилия клиента и телефона клиента.  
  
> [!TIP]
>  Можно обработать возвращаемое значение (выходной параметр) из хранимой процедуры. Дополнительные сведения и пример см. в разделе [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype).  
  
## <a name="see-also"></a>См. также  
 [Набор записей (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Набор записей: Выполнение обновления наборов записей (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)   
 [Набор записей: Объявление класса таблицы (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Набор записей. Объединение (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)