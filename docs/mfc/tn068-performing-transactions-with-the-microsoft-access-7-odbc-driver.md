---
title: 'TN068: Выполнение транзакций с драйвером Microsoft Access 7 ODBC'
ms.date: 06/28/2018
f1_keywords:
- vc.data.odbc
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
ms.openlocfilehash: 3121587f85c4ea19cc92e39569008b597d24ea58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363795"
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>TN068: Выполнение транзакций с драйвером Microsoft Access 7 ODBC

> [!NOTE]
> Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.

Эта заметка описывает способ выполнения транзакций, при использовании классов базы данных MFC ODBC и Microsoft Access 7.0 ODBC драйвера, включенного в пакет драйверов рабочего стола Microsoft ODBC версии 3.0.

## <a name="overview"></a>Обзор

Если приложение базы данных выполняет транзакции, будьте внимательны, чтобы вызвать `CDatabase::BeginTrans` и `CRecordset::Open` в правильной последовательности в приложении. Драйвер Microsoft Access 7.0 использует ядро СУБД Microsoft Jet и Jet требует, что приложение не запускает транзакцию в любой базе данных с открытым курсором. Для классов баз данных MFC ODBC, открытый курсор, равным открытую `CRecordset` объекта.

При открытии набора записей, перед вызовом `BeginTrans`, может не появиться сообщения об ошибках. Тем не менее, любой набор записей обновлениях делает ваши приложения, становятся постоянными после вызова метода `CRecordset::Update`, и обновления не откатываются, вызвав `Rollback`. Чтобы избежать этой проблемы, необходимо вызвать `BeginTrans` первой, а затем откройте набор записей.

MFC проверяет функциональные возможности драйвера для фиксации и отката режима работы курсоров. Класс `CDatabase` предоставляет две функции-члены, `GetCursorCommitBehavior` и `GetCursorRollbackBehavior`, чтобы определить влияние какой-либо транзакции на вашей открытым `CRecordset` объекта. Для драйвера Microsoft ODBC 7.0 доступа, эти функции-члены возвращают `SQL_CB_CLOSE` так, как драйвер для Access не поддерживает сохранение курсора. Таким образом, необходимо вызвать `CRecordset::Requery` следующие `CommitTrans` или `Rollback` операции.

Если вам нужно выполнять несколько транзакций, один за другим, нельзя вызывать `Requery` после первой транзакции и затем приступим к следующему. Необходимо закрыть записей до следующего вызова `BeginTrans` для удовлетворения требований требование Jet. Это техническое Примечание описаны два метода обработки такой ситуации:

- Закрытие набора записей после каждого `CommitTrans` или `Rollback` операции.

- С помощью функции ODBC API `SQLFreeStmt`.

## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>Закрытие набора записей после каждого CommitTrans или операция отката

Перед запуском транзакции, убедитесь, что объект recordset закрыт. После вызова метода `BeginTrans`, вызовите набора записей `Open` функция-член. Закройте набор записей сразу после вызова `CommitTrans` или `Rollback`. Обратите внимание на то, что многократное Открытие и закрытие набора записей может снизить производительность приложения.

## <a name="using-sqlfreestmt"></a>С помощью SQLFreeStmt

Можно также использовать функцию ODBC API `SQLFreeStmt` для явного закрытия курсора после завершения транзакции. Чтобы запустить другой транзакцией, вызовите `BeginTrans` следуют `CRecordset::Requery`. При вызове `SQLFreeStmt`, необходимо указать HSTMT набора записей в качестве первого параметра и *SQL_CLOSE* качестве второго параметра. Этот метод работает быстрее, чем закрытия и открытия набора записей в начале каждой транзакции. Следующий код демонстрирует реализацию этого метода:

```cpp
CMyDatabase db;
db.Open("MYDATASOURCE");
CMyRecordset rs(&db);

// start transaction 1 and
// open the recordset
db.BeginTrans();
rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans(); // or Rollback()

// close the cursor
::SQLFreeStmt(rs.m_hstmt, SQL_CLOSE);

// start transaction 2
db.BeginTrans();
// now get the result set
rs.Requery();

// manipulate data

// end transaction 2
db.CommitTrans();

rs.Close();
db.Close();
```

Другой способ реализации этой методики — для записи новая функция `RequeryWithBeginTrans`, которую можно вызвать, чтобы начать новую транзакцию после фиксации или отката первой. Чтобы написать такой функции, выполните следующие действия:

1. Скопируйте код для `CRecordset::Requery( )` новые функции.

2. Добавьте следующую строку сразу после вызова `SQLFreeStmt`:

   `m_pDatabase->BeginTrans( );`

Теперь можно вызвать эту функцию между каждой парой транзакций:

```cpp
// start transaction 1 and
// open the recordset
db.BeginTrans();

rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans();   // or Rollback()

// close the cursor, start new transaction,
// and get the result set
rs.RequeryWithBeginTrans();

// manipulate data

// end transaction 2
db.CommitTrans();   // or Rollback()
```

> [!NOTE]
> Не используйте этот метод, если вам нужно изменить переменные-члены набора записей *m_strFilter* или *m_strSort* между транзакциями. В этом случае следует закрыть набор записей после каждого `CommitTrans` или `Rollback` операции.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
