---
title: 'Транзакции: Выполнение транзакции в наборе записей (ODBC) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bd412549c86c3ca8ddc004016183b64248bdf292
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>Транзакции: выполнение транзакции в наборе записей (ODBC)
В этом разделе описывается выполнение транзакции в наборе записей.  
  
> [!NOTE]
>  Поддерживается только один уровень транзакций; Создание вложенных транзакций невозможно.  
  
#### <a name="to-perform-a-transaction-in-a-recordset"></a>Выполнение транзакции в наборе записей  
  
1.  Вызовите `CDatabase` объекта **BeginTrans** функции-члена.  
  
2.  Если не реализована массовая выборка строк, вызвать **AddNew или обновление**, **изменить или обновить**, и **удалить** один или несколько объектов набора записей в одной и той же функции-члены База данных, любое количество раз. Дополнительные сведения см. в разделе [набор записей: Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). Если групповая выборка строк реализована, необходимо написать собственные функции для обновления источника данных.  
  
3.  Наконец, вызовите `CDatabase` объекта **CommitTrans** функции-члена. При возникновении ошибки в одном из обновлений или необходимо отменить изменения, вызвать его **отката** функции-члена.  
  
 В следующем примере два набора записей для удаления регистрации Стьюдента из регистрации базы данных school, удаляются из всех классов, в которых зарегистрирован студент. Поскольку **удалить** вызовы в обоих наборах записей должна завершиться успешно, требуется транзакция. В примере предполагается существование `m_dbStudentReg`, переменную-член типа `CDatabase` уже подключен к источнику данных и классы набора записей `CEnrollmentSet` и `CStudentSet`. `strStudentID` Переменная содержит значение, полученное от пользователя.  
  
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
>  Вызов **BeginTrans** снова без вызова **CommitTrans** или **отката** является ошибкой.  
  
## <a name="see-also"></a>См. также  
 [Транзакция (ODBC)](../../data/odbc/transaction-odbc.md)   
 [Транзакция: Влияние транзакций на обновления (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase-класс](../../mfc/reference/cdatabase-class.md)   
 [Класс CRecordset](../../mfc/reference/crecordset-class.md)