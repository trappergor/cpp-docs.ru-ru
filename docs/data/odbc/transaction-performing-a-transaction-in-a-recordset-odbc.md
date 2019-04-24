---
title: 'Транзакции: Выполнение транзакции в наборе записей (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: 9e06d61d3d86233e136b0b3fe78f149a6778649b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035245"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>Транзакции: Выполнение транзакции в наборе записей (ODBC)

В этом разделе объясняется, как выполнять транзакции в наборе записей.

> [!NOTE]
>  Поддерживается только один уровень транзакций; нельзя вкладывать транзакции.

#### <a name="to-perform-a-transaction-in-a-recordset"></a>Выполнение транзакции в наборе записей

1. Вызовите `CDatabase` объекта `BeginTrans` функция-член.

1. Если вы не реализовали выборка строк, вызвать `AddNew/Update`, `Edit/Update`, и `Delete` функции-члены один или несколько объектов набора записей той же базы данных столько раз, при необходимости. Дополнительные сведения см. в разделе [набор записей: Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). Если вы реализовали групповая выборка строк, необходимо написать собственные функции для обновления источника данных.

1. Наконец, вызовите `CDatabase` объекта `CommitTrans` функция-член. Если вы решите отменить изменения в одно из обновлений возникает ошибка, вызовите его `Rollback` функция-член.

В следующем примере два набора записей используется для удаления регистрации учащихся из регистрации базы данных school, удаляются из всех классов, в которых зарегистрирован студент. Так как `Delete` вызовов в обоих наборах записей должна завершиться успешно, необходима транзакция. В примере предполагается существование `m_dbStudentReg`, переменную-член типа `CDatabase` уже подключен к источнику данных и классы набора записей `CEnrollmentSet` и `CStudentSet`. `strStudentID` Переменная содержит значение, полученное от пользователя.

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
>  Вызов `BeginTrans` еще раз без вызова `CommitTrans` или `Rollback` является ошибкой.

## <a name="see-also"></a>См. также

[Транзакция (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[Транзакции: Влияние транзакций на обновления (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[Класс CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)