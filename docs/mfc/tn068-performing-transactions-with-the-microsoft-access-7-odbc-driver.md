---
title: 'TN068: Выполнение транзакций с драйвером Microsoft Access 7 ODBC | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.data.odbc
dev_langs:
- C++
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 63cce7532d93b1bd44b6a44c526310bd894d5e07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>TN068. Выполнение транзакций с драйвером Microsoft Access 7 ODBC
> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
 Эта заметка описывает, как для выполнения транзакций, при использовании классов баз данных MFC ODBC и драйвер ODBC 7.0 доступа Microsoft, включенные в пакет драйверов рабочего стола Microsoft ODBC версии 3.0.  
  
## <a name="overview"></a>Обзор  
 Если приложение базы данных выполняет операции, будьте внимательны, чтобы вызвать `CDatabase::BeginTrans` и `CRecordset::Open` в правильной последовательности в приложении. Драйвер Microsoft Access 7.0 использует базы данных Microsoft Jet, а Jet требует, что приложение не начать транзакцию в любой базе данных с открытым курсором. Для классов баз данных MFC ODBC, открытый курсор приравнивается к открытой `CRecordset` объекта.  
  
 При открытии набора записей перед вызовом **BeginTrans**, могут не отображаться сообщения об ошибках. Однако любого набора записей обновления делает вашего приложения, становятся постоянными после вызова `CRecordset::Update`, и обновления не откатываются, вызвав **отката**. Чтобы избежать этой проблемы, необходимо вызвать **BeginTrans** первой, а затем откройте набор записей.  
  
 MFC проверяет драйвер функциональные возможности для фиксации и отката режима работы курсоров. Класс `CDatabase` предоставляет две функции-члена, `GetCursorCommitBehavior` и `GetCursorRollbackBehavior`, чтобы определить влияние любой транзакции на ваш открыть `CRecordset` объекта. Для драйвера Microsoft ODBC 7.0 доступа, эти функции-члены возвращают `SQL_CB_CLOSE` драйвер доступа поддерживает сохранение курсора. Поэтому необходимо вызвать метод `CRecordset::Requery` следующие **CommitTrans** или **отката** операции.  
  
 Если нужно будет выполнять несколько транзакций друг за другом невозможно вызвать **Requery** после первой транзакции и запуска следующего. Необходимо закрыть записей до следующего вызова **BeginTrans** для удовлетворения требований Jet. Это техническое Примечание описывает два способа обработки этой ситуации:  
  
-   Закрытие набора записей после каждого **CommitTrans** или **отката** операции.  
  
-   С помощью функции API-интерфейса ODBC **SQLFreeStmt**.  
  
## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>Закрытие набора записей после каждой CommitTrans или операция отката  
 Перед запуском транзакции, убедитесь, что закрыты объекта набора записей. После вызова метода **BeginTrans**, вызовите набора записей **откройте** функции-члена. Закройте набор записей сразу после вызова **CommitTrans** или **отката**. Обратите внимание, что повторного открытия и закрытия набора записей может привести к снижению производительности приложения.  
  
## <a name="using-sqlfreestmt"></a>С помощью SQLFreeStmt  
 Можно также использовать функцию ODBC API **SQLFreeStmt** явно закрыть курсор после завершения транзакции. Чтобы запустить другой транзакцией, вызовите **BeginTrans** следуют `CRecordset::Requery`. При вызове **SQLFreeStmt**, необходимо указать HSTMT набора записей в качестве первого параметра и **SQL_CLOSE** в качестве второго параметра. Этот метод работает быстрее, чем закрытия и открытия набора записей в начале каждой транзакции. Следующий код демонстрирует, как реализовать этот метод:  
  
```  
CMyDatabase db;  
db.Open("MYDATASOURCE");

CMyRecordset rs(&db);

 
// start transaction 1 and   
// open the recordset  
db.BeginTrans();

rs.Open();

 
// manipulate data  
 
// end transaction 1  
db.CommitTrans();
*// or Rollback()  
 
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
  
 Это реализуется другим способом является создания новой функции **RequeryWithBeginTrans**, который можно вызвать для запуска следующей транзакции после фиксации или отката первой. Для написания такой функции, выполните следующие действия:  
  
1.  Скопируйте код для **(метод CRecordset::Requery)** новой функции.  
  
2.  Добавьте следующую строку сразу после вызова **SQLFreeStmt**:  
  
 `m_pDatabase->BeginTrans( );`  
  
 Теперь можно вызвать эту функцию между каждой парой транзакций:  
  
```  
// start transaction 1 and   
// open the recordset  
db.BeginTrans();

rs.Open();

 
// manipulate data  
 
// end transaction 1  
db.CommitTrans();
*// or Rollback()  
 
// close the cursor,
    start new transaction,  
// and get the result set  
rs.RequeryWithBeginTrans();

 
// manipulate data  
 
// end transaction 2  
db.CommitTrans();
*// or Rollback()  
```  
  
> [!NOTE]
>  Не используйте этот метод, если вам нужно изменить переменных-членов набора записей **m_strFilter** или `m_strSort` между транзакциями. В этом случае следует закрыть набора записей после каждого **CommitTrans** или **отката** операции.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

