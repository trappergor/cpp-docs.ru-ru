---
title: 'Транзакции: выполнение транзакции в наборе записей (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: 45ae414c318376b2c4d787498e9a288a0037af83
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358097"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>Транзакции: выполнение транзакции в наборе записей (ODBC)

В этой теме объясняется, как выполнять транзакцию в рекордном наборе.

> [!NOTE]
> Поддерживается только один уровень транзакций; вы не можете гнездить транзакции.

#### <a name="to-perform-a-transaction-in-a-recordset"></a>Выполнение транзакции в рекордном наборе

1. Вызовите функцию `CDatabase` `BeginTrans` члена объекта.

1. Если вы не реализовали объем строки извлечения, позвоните, `AddNew/Update` `Edit/Update`и `Delete` функции участника одного или нескольких объектов записи одной или той же базы данных столько раз, сколько необходимо. Для получения дополнительной информации см. [Recordset: Добавление, обновление и утихшие записи (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). Если вы реализовали объемстроки извлечения, вы должны написать свои собственные функции для обновления источника данных.

1. Наконец, `CDatabase` позвоните `CommitTrans` функции члена объекта. Если в одном из обновлений произошла ошибка или `Rollback` вы решили отменить изменения, позвоните в функцию ее члена.

В следующем примере используются два набора записей для удаления зачисления ученика из базы данных регистрации школы, удаляя ученика из всех классов, в которых студент зачислен. Поскольку `Delete` вызовы в обоих рекордных наборах должны быть успешными, требуется транзакция. Пример `m_dbStudentReg`предполагает существование переменной типа, `CDatabase` уже подключенной к источнику данных, `CEnrollmentSet` `CStudentSet`а также классов регистрации и . Переменная `strStudentID` содержит значение, полученное от пользователя.

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
> Вызов `BeginTrans` снова `CommitTrans` без `Rollback` вызова или является ошибкой.

## <a name="see-also"></a>См. также раздел

[Транзакция (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[Транзакция. Влияние транзакций на обновления (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[Класс CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)
