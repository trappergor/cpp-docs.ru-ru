---
title: "Структура CDaoTableDefInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoTableDefInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoTableDefInfo - структура"
  - "доступ к данным DAO.NET, TableDefs - коллекция"
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Структура CDaoTableDefInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `CDaoTableDefInfo` содержит сведения о конкретном объекте tabledef \(DAO\) для объектов доступа к данным.  
  
## Синтаксис  
  
```  
  
      struct CDaoTableDefInfo  
{  
   CString m_strName;               // Primary  
   BOOL m_bUpdatable;               // Primary  
   long m_lAttributes;              // Primary  
   COleDateTime m_dateCreated;      // Secondary  
   COleDateTime m_dateLastUpdated;  // Secondary  
   CString m_strSrcTableName;       // Secondary  
   CString m_strConnect;            // Secondary  
   CString m_strValidationRule;     // All  
   CString m_strValidationText;     // All  
   long m_lRecordCount;             // All  
};  
```  
  
#### Параметры  
 `m_strName`  
 Объект tabledef уникальные имена.  Для получения значения этого свойства непосредственно вызовите функцию\-член [GetName](../Topic/CDaoTableDef::GetName.md) объекта tabledef.  Дополнительные сведения см. в разделе «свойство» Имя» в справке DAO.  
  
 `m_bUpdatable`  
 Указывает, является ли изменения можно внести в таблице.  Быстро определить, является ли таблица обновляемого открыть объект `CDaoTableDef` таблицы и вызов функции\-члена [CanUpdate](../Topic/CDaoTableDef::CanUpdate.md) объекта.  `CanUpdate` всегда возвращает отличное от нуля \(**TRUE**\) для только что созданных объектов и 0 tabledef \(**ЛОЖЬ**\) для подключенного объекта tabledef.  Новый объект tabledef можно добавить только в базе данных, для которой текущий пользователь имеет разрешение на запись  Если таблица содержит только nonupdatable поля, `CanUpdate` возвращает 0.  Если одно или несколько полей записи, `CanUpdate` возвращает отлично от нуля.  Правка можно только обновляемого поля.  Дополнительные сведения см. в разделе «обновляемого свойства» в справке DAO.  
  
 `m_lAttributes`  
 Определяет характеристики таблицы, представленной объектом tabledef.  Для извлечения текущих атрибуты tabledef вызовите функцию\-член [GetAttributes](../Topic/CDaoTableDef::GetAttributes.md).  Возвращенное значение может быть сочетанием из этих длинные знаковые константы \(с помощью bitwise\- ИЛИ \(  **&#124;**\) оператор\).  
  
-   **dbAttachExclusive** для баз данных, использующих ядра СУБД Microsoft Jet, указывает, что таблица подключенная таблице раскрытая в монопольном режиме.  
  
-   **dbAttachSavePWD** для баз данных, использующих ядра СУБД Microsoft Jet, показывает, что идентификатор пользователя и пароль для таблицы подключенной сохраняются со сведениями о соединении.  
  
-   **dbSystemObject** означает, что таблица системная таблица возможностях ядра СУБД Microsoft Jet. \(только для чтения\).  
  
-   **dbHiddenObject** означает, что таблица скрытая таблице возможностях ядра СУБД Microsoft Jet \(для временного использования\). \(только для чтения\).  
  
-   **dbAttachedTable** означает, что таблица подключенная таблицы из базы данных, ODBC, например базы данных paradox.  
  
-   **dbAttachedODBC** означает, что таблица подключенная таблицы из базы данных ODBC, например Microsoft SQL Server.  
  
 `m_dateCreated`  
 Дата и время таблица была создана.  Непосредственно для извлечения даты созданной таблице, вызовите функцию\-член [GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md) объекта `CDaoTableDef`, связанного с таблицей.  См. комментарии, приведенный ниже.  Дополнительные сведения см. в разделе «DateCreated, свойства LastUpdated» в справке DAO.  
  
 `m_dateLastUpdated`  
 Дата и время последней, сделанного изменения в структуре таблицы.  Непосредственно для извлечения даты последнего таблица была обновлена, вызовите функцию\-член [GetDateLastUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md) объекта `CDaoTableDef`, связанного с таблицей.  См. комментарии, приведенный ниже.  Дополнительные сведения см. в разделе «DateCreated, свойства LastUpdated» в справке DAO.  
  
 *m\_strSrcTableName*  
 Указывает имя подключенной таблицы, если таковые имеются.  Непосредственно для получения имени таблицы источника, вызовите функцию\-член [GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md) объекта `CDaoTableDef`, связанного с таблицей.  
  
 `m_strConnect`  
 Сведения об источнике открытой базы данных.  Это можно проверить свойство, вызвав функцию\-член [GetConnect](../Topic/CDaoTableDef::GetConnect.md) объекта класса `CDaoTableDef`.  Дополнительные сведения о строки подключения см. в разделе `GetConnect`.  
  
 `m_strValidationRule`  
 Значение, которое проверяет данные в полях tabledef по мере их изменения или добавляются в таблицу.  Проверка поддерживается только для баз данных, использующих ядра СУБД Microsoft Jet.  Непосредственно для извлечения правило проверки, вызовите функцию\-член [GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md) объекта `CDaoTableDef`, связанного с таблицей.  Дополнительные сведения см. в разделе «свойство ValidationRule» в справке DAO.  
  
 `m_strValidationText`  
 Значение, указывающее текст сообщения, если приложению необходимо отобразить правило проверки, заданное свойством ValidationRule не выполняется.  Дополнительные сведения см. в разделе «свойство ValidationText» в справке DAO.  
  
 *m\_lRecordCount*  
 Количество записей обращение к элементу в объекте tabledef.  Этот параметр свойства только для чтения.  Непосредственно для извлечения record число, вызовите функцию\-член [GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md) объекта `CDaoTableDef`.  Документация по `GetRecordCount` описывает record число включен.  Обратите внимание, что получить это число может быть длительной операцией, если таблица содержит много записей.  
  
## Заметки  
 Tabledef объект класса [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md).  Ссылки на первичный, вторичный и всем выше показано, как сведения возвращаются функцией\-членом [GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md) в классе `CDaoDatabase`.  
  
 Сведения, функцией\-членом [CDaoDatabase::GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md) хранятся в структуре `CDaoTableDefInfo`.  Вызовите функцию\-член `GetTableDefInfo` объекта `CDaoDatabase` в коллекции, TableDefs хранится объект tabledef.  `CDaoTableDefInfo` также определяет функции\-члена `Dump` выполняется в режиме построения.  Можно использовать `Dump` сбросить содержимое объекта `CDaoTableDefInfo`.  
  
 Параметры даты и времени, являются производными от компьютера, на котором была создана базовая таблица или последнего обновления.  В многопользовательской среде, пользователи должны получить эти параметры, чтобы непосредственно из файлового сервера избежали несоответствий в параметрах свойств DateCreated и LastUpdated.  
  
## Требования  
 **Header:** afxdao.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef::CanUpdate](../Topic/CDaoTableDef::CanUpdate.md)   
 [CDaoTableDef::GetAttributes](../Topic/CDaoTableDef::GetAttributes.md)   
 [CDaoTableDef::GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md)   
 [CDaoTableDef::GetDateLastUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md)   
 [CDaoTableDef::GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md)   
 [CDaoTableDef::GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md)   
 [CDaoTableDef::GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md)   
 [CDaoTableDef::GetValidationText](../Topic/CDaoTableDef::GetValidationText.md)