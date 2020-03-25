---
title: 'Транзакции: выполнение транзакции в наборе записей (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: 94177a27a1f99a8c9c37b7fce3f697fd0088b7c6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212593"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>Транзакции: выполнение транзакции в наборе записей (ODBC)

В этом разделе объясняется, как выполнить транзакцию в наборе записей.

> [!NOTE]
>  Поддерживается только один уровень транзакций; вложенные транзакции не допускают.

#### <a name="to-perform-a-transaction-in-a-recordset"></a>Выполнение транзакции в наборе записей

1. Вызовите функцию члена `BeginTrans` объекта `CDatabase`.

1. Если не реализована многострочная выборка строк, вызывайте `AddNew/Update`, `Edit/Update`и `Delete` функции члена одного или нескольких объектов набора записей одной и той же базы данных столько раз, сколько необходимо. Дополнительные сведения см. в разделе [набор записей: Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). При реализации групповой выборки строк необходимо написать собственные функции для обновления источника данных.

1. Наконец, вызовите функцию члена `CommitTrans` объекта `CDatabase`. Если в одном из обновлений возникает ошибка или вы решили отменить изменения, вызовите ее `Rollback` функцию члена.

В следующем примере используются два набора записей для удаления регистрации учащегося из базы данных регистрации учебного заведения, удаление учащегося из всех классов, в которых зарегистрирован студент. Так как `Delete` вызовы в обоих наборах записей должны быть выполнены, требуется транзакция. В примере предполагается существование `m_dbStudentReg`, переменная-член типа `CDatabase` уже подключена к источнику данных, а также классы наборов записей `CEnrollmentSet` и `CStudentSet`. Переменная `strStudentID` содержит значение, полученное от пользователя.

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
>  Повторный вызов `BeginTrans` без вызова `CommitTrans` или `Rollback` является ошибкой.

## <a name="see-also"></a>См. также раздел

[Транзакция (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[Транзакция. Влияние транзакций на обновления (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[Класс CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)
