---
title: "TN068. Выполнение транзакций с драйвером Microsoft Access 7 ODBC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.data.odbc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN068"
  - "транзакции, вызов BeginTrans"
  - "транзакции, Microsoft Access"
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN068. Выполнение транзакций с драйвером Microsoft Access 7 ODBC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию.  В результате некоторые процедуры и разделы могут быть устаревшими или неверными.  Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
 Эта заметка выполнение транзакции при использовании классов баз данных MFC ODBC и Microsoft Access 7.0 драйверов ODBC, поставляемых с версии 3.0 пакета рабочего стола драйвера Microsoft ODBC.  
  
## Обзор  
 Если приложение баз данных выполняет транзакции, необходимо соблюдать осторожность при `CDatabase::BeginTrans` и `CRecordset::Open` в правильной последовательности в приложении.  Драйвер Microsoft Access 7.0 использует ядра СУБД Microsoft Jet и двигатель требует, чтобы приложение начинает транзакцию в любой базе данных, которая имеет открытый курсор.  Для классов баз данных MFC ODBC открытый курсор равно в открытый `CRecordset` объект.  
  
 Если открыть набор записей до вызова функции **BeginTrans**, не могут отображаться все сообщения об ошибках.  Однако любой набор записей обновляет приложение принимает быть константной после вызова `CRecordset::Update` и обновления не будут откачены с помощью метода **Откат**.  Чтобы избежать этой проблемы, необходимо вызвать метод **BeginTrans**, а затем открыть набор записей.  
  
 MFC функция проверяет драйвера для фиксации курсора и расширения функциональности отката.  Класс `CDatabase` предоставляет 2 функцию\-член, `GetCursorCommitBehavior` и `GetCursorRollbackBehavior`, для определения результата любой транзакции в открытом объекте `CRecordset`.  Для драйвера Microsoft Access 7.0 ODBC, эти функции\-члены возвращают `SQL_CB_CLOSE`, поскольку драйвер доступа не поддерживает сохранение курсора.  Поэтому необходимо вызвать `CRecordset::Requery` после операции **CommitTrans** или **Откат**.  
  
 Если требуется выполнить несколько транзакций один за другим, невозможно вызвать **Requery** после первой транзакции, а затем запустите следующие значения.  Необходимо закрыть набор записей до следующий вызов **BeginTrans** для удовлетворения требования к jet.  Это техническое примечание описывает 2 метода обработки подобной ситуации:  
  
-   Закрыть набор записей после каждой операции **CommitTrans** или **Откат**.  
  
-   С помощью функции API ODBC **SQLFreeStmt**.  
  
## Закрыть набор записей или после каждого CommitTrans операции отката  
 Перед запуском транзакции, убедитесь, что объект набора записей закрыт.  После вызова **BeginTrans**, вызовите функцию\-член **Открыть** набора записей.  Закройте набор записей сразу после вызова метода **CommitTrans** или **Откат**.  Обратите внимание, что повторного открытия и закрытия набор записей могут уменьшение производительности приложения.  
  
## Использование SQLFreeStmt  
 Можно также использовать функцию интерфейса API ODBC **SQLFreeStmt** явно закрыть курсор после завершения транзакции.  Для запуска другая транзакция вызовите функцию **BeginTrans** с `CRecordset::Requery`.  При вызове **SQLFreeStmt**, необходимо указать HSTMT набора записей в качестве первого параметра и **SQL\_CLOSE** в качестве второго параметра.  Этот метод быстрее, чем открытие и закрытие набор записей в начале каждой транзакции.  В следующем примере демонстрируется, как реализовать этот метод.  
  
```  
CMyDatabase db;  
db.Open( "MYDATASOURCE" );  
CMyRecordset rs( &db );  
  
// start transaction 1 and   
// open the recordset  
db.BeginTrans( );  
rs.Open( );  
  
// manipulate data  
  
// end transaction 1  
db.CommitTrans( );  // or Rollback( )  
  
// close the cursor  
::SQLFreeStmt( rs.m_hstmt, SQL_CLOSE );  
  
// start transaction 2  
db.BeginTrans( );  
  
// now get the result set  
rs.Requery( );  
  
// manipulate data  
  
// end transaction 2  
db.CommitTrans( );  
  
rs.Close( );  
db.Close( );  
```  
  
 Другой способ реализации этого метода создать новую функцию **RequeryWithBeginTrans**, который можно вызывать для запуска следующей транзакции после фиксации или отката первый из них.  Для записи такой функции выполните следующие действия.  
  
1.  Скопируйте код в **CRecordset::Requery \(\)** в новой функции.  
  
2.  Добавьте следующую линия сразу после вызова метода **SQLFreeStmt**.  
  
     `m_pDatabase->BeginTrans( );`  
  
 Теперь можно вызвать эту функцию между каждой парой транзакций:  
  
```  
// start transaction 1 and   
// open the recordset  
db.BeginTrans( );  
rs.Open( );  
  
// manipulate data  
  
// end transaction 1  
db.CommitTrans( );  // or Rollback( )  
  
// close the cursor, start new transaction,  
// and get the result set  
rs.RequeryWithBeginTrans( );  
  
// manipulate data  
  
// end transaction 2  
db.CommitTrans( );  // or Rollback( )  
```  
  
> [!NOTE]
>  Не используйте этот метод, если требуется изменить переменные\-члены **m\_strFilter** или `m_strSort` набора записей между транзакциями.  В этом случае необходимо закрыть набор записей после каждой операции **CommitTrans** или **Откат**.  
  
## См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)