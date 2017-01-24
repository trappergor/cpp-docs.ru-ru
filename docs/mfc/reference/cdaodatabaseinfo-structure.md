---
title: "Структура CDaoDatabaseInfo | Microsoft Docs"
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
  - "CDaoDatabaseInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoDatabaseInfo - структура"
  - "доступ к данным DAO.NET, коллекция баз данных"
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура CDaoDatabaseInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `CDaoDatabaseInfo` содержит сведения об объекте базы данных, указанном для объектов \(DAO\) доступа к данным.  
  
## Синтаксис  
  
```  
  
      struct CDaoDatabaseInfo  
{  
   CString m_strName;       // Primary  
   BOOL m_bUpdatable;       // Primary  
   BOOL m_bTransactions;    // Primary  
   CString m_strVersion;    // Secondary  
   long m_lCollatingOrder;  // Secondary  
   short m_nQueryTimeout;   // Secondary  
   CString m_strConnect;    // All  
};  
```  
  
#### Параметры  
 `m_strName`  
 Уникальные имена объекта базы данных.  Непосредственно для извлечения это свойство, вызовите метод [CDaoDatabase::GetName](../Topic/CDaoDatabase::GetName.md).  Дополнительные сведения см. в разделе «свойство» Имя» в справке DAO.  
  
 `m_bUpdatable`  
 Указывает, является ли изменения можно внести в базе данных.  Непосредственно для извлечения это свойство, вызовите метод [CDaoDatabase::CanUpdate](../Topic/CDaoDatabase::CanUpdate.md).  Дополнительные сведения см. в разделе «обновляемого свойства» в справке DAO.  
  
 *m\_bTransactions*  
 Указывает, поддерживает ли источник данных транзакции — запись последовательности изменений, можно будет отменено откатить \(\) или сохранить \(сохраненный\).  Если база данных основана на ядра СУБД Microsoft Jet, свойство транзакций отлично от нуля и можно использовать транзакции.  Другие ядра СУБД не поддерживают транзакции.  Непосредственно для извлечения это свойство, вызовите метод [CDaoDatabase::CanTransact](../Topic/CDaoDatabase::CanTransact.md).  Дополнительные сведения см. в разделе «свойство транзакций» в справке DAO.  
  
 *m\_strVersion*  
 Отображает версию ядра СУБД Microsoft Jet.  Для получения значения этого свойства непосредственно вызовите функцию\-член [GetVersion](../Topic/CDaoDatabase::GetVersion.md) объекта базы данных.  Дополнительные сведения см. в разделе «свойство версии» в справке DAO.  
  
 `m_lCollatingOrder`  
 Определяет последовательность порядка сортировки в текст для сравнения строк или сортировки.  Возможные допустимые значения приведены ниже.  
  
-   использование **dbSortGeneral** общий \(английский, французский, немецкий, итальянский, португалка и современный испанский язык\) порядок сортировки.  
  
-   использование **dbSortArabic** арабский порядок сортировки.  
  
-   использование **dbSortCyrillic** русский порядок сортировки.  
  
-   использование **dbSortCzech** чешский порядок сортировки.  
  
-   использование **dbSortDutch**  голландский порядок сортировки.  
  
-   использование **dbSortGreek** греческий порядок сортировки.  
  
-   использование **dbSortHebrew** иврит порядок сортировки.  
  
-   использование **dbSortHungarian** венгерский порядок сортировки.  
  
-   использование **dbSortIcelandic** исландский порядок сортировки.  
  
-   использование **dbSortNorwdan** норвежский или датский порядок сортировки.  
  
-   использование **dbSortPDXIntl** порядок сортировки международная paradox.  
  
-   использование **dbSortPDXNor** порядок сортировки paradox норвежский или датский.  
  
-   использование **dbSortPDXSwe** порядок сортировки paradox шведский или финский.  
  
-   использование **dbSortPolish** польский порядок сортировки.  
  
-   использование **dbSortSpanish** испанский порядок сортировки.  
  
-   использование **dbSortSwedFin** шведский или финский порядок сортировки.  
  
-   использование **dbSortTurkish** турецкий порядок сортировки.  
  
-   не указано **dbSortUndefined** порядок сортировки или неисвестне.  
  
 Дополнительные сведения см. в разделе «настраивая параметры реестра Windows для доступа к данным» в справке DAO.  
  
 *m\_nQueryTimeout*  
 Количество секунд ядра СУБД Microsoft Jet ожидает до возникновения ошибки истечения времени ожидания происходит при выполнении запроса на базе данных ODBC.  Значение времени ожидания по умолчанию составляет 60 секунд.  Когда QueryTimeout присвоено значение 0, время ожидания не происходит. это может вызвать программу перестать отвечать.  Для получения значения этого свойства непосредственно вызовите функцию\-член [GetQueryTimeout](../Topic/CDaoDatabase::GetQueryTimeout.md) объекта базы данных.  Дополнительные сведения см. в разделе «свойство QueryTimeout» в справке DAO.  
  
 `m_strConnect`  
 Сведения об источнике открытой базы данных.  Дополнительные сведения о подключении строки, а также сведения о извлечь значение этого свойства непосредственно см. в описании функции\-члена [CDaoDatabase::GetConnect](../Topic/CDaoDatabase::GetConnect.md).  Дополнительные сведения см. в разделе «свойства соединения» в справке DAO.  
  
## Заметки  
 База данных объект DAO основного объекта в основе MFC класса [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md).  Ссылки на первичный, вторичный и всем выше показано, как сведения возвращаются функцией\-членом [CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md).  
  
 Сведения, функцией\-членом [CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md) хранятся в структуре `CDaoDatabaseInfo`.  Вызовите `GetDatabaseInfo` для объекта `CDaoWorkspace`, в котором коллекции баз данных хранится объект базы данных.  `CDaoDatabaseInfo` также определяет функции\-члена `Dump` выполняется в режиме построения.  Можно использовать `Dump` сбросить содержимое объекта `CDaoDatabaseInfo`.  
  
## Требования  
 **Header:** afxdao.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace::GetDatabaseCount](../Topic/CDaoWorkspace::GetDatabaseCount.md)