---
title: "Структура CDaoDatabaseInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoDatabaseInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoDatabaseInfo structure
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ed7eb8612099daf59cb7e722434102095122f3d1
ms.lasthandoff: 02/24/2017

---
# <a name="cdaodatabaseinfo-structure"></a>Структура CDaoDatabaseInfo
`CDaoDatabaseInfo` Структура содержит сведения об объекте базы данных, определенные для объектов доступа к данным (DAO).  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `m_strName`  
 Однозначно имена объектов базы данных. Для получения этого свойства непосредственно вызвать [CDaoDatabase::GetName](../../mfc/reference/cdaodatabase-class.md#getname). Дополнительные сведения см. в разделе «Свойства Name» в справке DAO.  
  
 `m_bUpdatable`  
 Указывает, может ли внесены изменения в базу данных. Для получения этого свойства непосредственно вызвать [CDaoDatabase::CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate). Дополнительные сведения см. в разделе «Обновляемые свойства» в справке DAO.  
  
 *m_bTransactions*  
 Указывает, поддерживает ли источник данных транзакций — запись ряд изменений, которые можно позднее откат (отменено) или фиксации (Сохранить). Если база данных основана на базы данных Microsoft Jet, свойство транзакции имеет ненулевое значение, и транзакции можно использовать. Другие ядра СУБД может не поддерживать транзакции. Для получения этого свойства непосредственно вызвать [CDaoDatabase::CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact). Дополнительные сведения см. в разделе «Свойство транзакции» в справке DAO.  
  
 *m_strVersion*  
 Указывает версию базы данных Microsoft Jet. Чтобы получить значение этого свойства напрямую, вызовите объект базы данных [GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion) функции-члена. Дополнительные сведения см. в разделе «Свойство Version» в справке DAO.  
  
 `m_lCollatingOrder`  
 Указывает последовательность сортировки в текст для сравнения строк или сортировки. Возможные допустимые значения приведены ниже.  
  
- **dbSortGeneral** использовать общий порядок сортировки (английский, французский, немецкий, португальский, итальянский и испанский современных).  
  
- **dbSortArabic** используется порядок сортировки для арабского языка.  
  
- **dbSortCyrillic** используется порядок сортировки русский.  
  
- **dbSortCzech** используется порядок сортировки чешский.  
  
- **dbSortDutch** использовать голландский сортировку.  
  
- **dbSortGreek** использовать греческие сортировку.  
  
- **dbSortHebrew** используется порядок сортировки иврита.  
  
- **dbSortHungarian** используется порядок сортировки венгерский.  
  
- **dbSortIcelandic** использовать Исландский сортировку.  
  
- **dbSortNorwdan** использовать порядок сортировки норвежский или датского языка.  
  
- **dbSortPDXIntl** используется порядок сортировки Paradox International.  
  
- **dbSortPDXNor** использовать Paradox норвежский или порядок сортировки для датского языка.  
  
- **dbSortPDXSwe** использовать Paradox шведский или финский сортировку.  
  
- **dbSortPolish** использовать порядок сортировки для польского языка.  
  
- **dbSortSpanish** используется порядок сортировки.  
  
- **dbSortSwedFin** используется порядок сортировки на шведский или финский язык.  
  
- **dbSortTurkish** используется порядок сортировки для турецкого языка.  
  
- **dbSortUndefined** порядок сортировки не определено или unknown.  
  
 Дополнительные сведения см. в разделе «Настройка Windows реестра параметры для доступа к данным» в справке DAO.  
  
 *m_nQueryTimeout*  
 Количество секунд ожидания перед тайм-аута базы данных Microsoft Jet возникает при запуске запроса в базе данных ODBC. Значение времени ожидания по умолчанию составляет 60 секунд. Когда QueryTimeout равным 0, происходит без времени ожидания; Это может привести к зависанию программы. Чтобы получить значение этого свойства напрямую, вызовите объект базы данных [GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) функции-члена. Дополнительные сведения см. в разделе «QueryTimeout свойство» в справке DAO.  
  
 `m_strConnect`  
 Предоставляет сведения об источнике открыть базу данных. Для получения сведений о объединение строк и сведения о получении значения этого свойства непосредственно в разделе [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) функции-члена. Дополнительные сведения см. в разделе «Свойства подключения», в справке DAO.  
  
## <a name="remarks"></a>Примечания  
 База данных является объект DAO базового объекта MFC класса [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md). Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются сведения по [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) функции-члена.  
  
 Данные, полученные по [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) функции-члена хранится в `CDaoDatabaseInfo` структуру. Вызов `GetDatabaseInfo` для `CDaoWorkspace` объектов, в которых коллекции баз данных хранится объект базы данных. `CDaoDatabaseInfo`также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для вывода содержимого из `CDaoDatabaseInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)   
 [Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)

