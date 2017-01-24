---
title: "Транзакции: выполнение транзакции в наборе записей (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "транзакции, обновление записей"
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Транзакции: выполнение транзакции в наборе записей (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В данном разделе описывается способ выполнения транзакции в наборе записей.  
  
> [!NOTE]
>  Поддерживаются только одноуровневые транзакции; создание вложенных транзакций невозможно.  
  
#### Выполнение транзакции в наборе записей  
  
1.  Вызовите функцию\-член **BeginTrans** объекта `CDatabase`.  
  
2.  Если групповая выборка строк не реализована, следует вызвать функции\-члены **AddNew\/Update**, **Edit\/Update** и **Delete** одного или нескольких объектов наборов записей, относящихся к одной базе данных, необходимое число раз.  Дополнительные сведения см. в разделе [Набор данных: добавление, обновление и удаление записей \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).  Если групповая выборка строк реализована, необходимо создать собственные функции для обновления источника данных.  
  
3.  Наконец, вызовите функцию\-член **CommitTrans** объекта `CDatabase`.  Если при обновлении произошла ошибка или необходимо отменить изменения, следует вызвать функцию\-член **Rollback** объекта.  
  
 В следующем примере используются два набора записей для удаления сведений об учащемся из регистрационной базы школы, причем сведения удаляются из всех классов.  Поскольку вызовы **Delete** должны завершиться успешно в обоих наборах записей, требуется выполнение транзакции.  В примере предполагается наличие базы данных `m_dbStudentReg`, переменной\-члена типа `CDatabase`, уже подключенной к источнику данных, и классов наборов записей `CEnrollmentSet` и `CStudentSet`.  Переменная `strStudentID` содержит значение, предоставленное пользователем.  
  
```  
BOOL CEnrollDoc::RemoveStudent( CString strStudentID )  
{  
    // remove student from all the classes  
    // the student is enrolled in  
  
    if ( !m_dbStudentReg.BeginTrans( ) )  
        return FALSE;  
  
    CEnrollmentSet rsEnrollmentSet(&m_dbStudentReg);  
    rsEnrollmentSet.m_strFilter = "StudentID = " + strStudentID;  
  
    if ( !rsEnrollmentSet.Open(CRecordset::dynaset) )  
        return FALSE;  
  
    CStudentSet rsStudentSet(&m_dbStudentReg);  
    rsStudentSet.m_strFilter = "StudentID = " + strStudentID;  
  
    if ( !rsStudentSet.Open(CRecordset::dynaset) )  
        return FALSE;  
  
    TRY  
    {  
        while ( !rsEnrollmentSet.IsEOF( ) )  
        {  
            rsEnrollmentSet.Delete( );  
            rsEnrollmentSet.MoveNext( );  
        }  
  
        // delete the student record  
        rsStudentSet.Delete( );  
  
        m_dbStudentReg.CommitTrans( );  
    }  
  
    CATCH_ALL(e)  
    {  
        m_dbStudentReg.Rollback( );  
        return FALSE;  
    }  
    END_CATCH_ALL  
  
    rsEnrollmentSet.Close( );  
    rsStudentSet.Close( );  
  
    return TRUE;  
  
}  
```  
  
> [!NOTE]
>  Повторный вызов метода **BeginTrans**, не сопровождаемый вызовом **CommitTrans** или **Rollback**, приведет к ошибке.  
  
## См. также  
 [Транзакция \(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [Транзакция. Влияние транзакций на обновления \(ODBC\)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Class](../Topic/CRecordset%20Class.md)