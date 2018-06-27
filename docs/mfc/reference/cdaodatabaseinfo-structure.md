---
title: Структура CDaoDatabaseInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoDatabaseInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoDatabaseInfo structure [MFC]
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b10cd2d5c6174e63ff8aa74b4edc98b20375fae0
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951937"
---
# <a name="cdaodatabaseinfo-structure"></a>Структура CDaoDatabaseInfo
`CDaoDatabaseInfo` Структура содержит сведения об объекте базы данных, определенных для объекты доступа к данным (DAO).  
  
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
 *m_strName*  
 Однозначно имен объектов базы данных. Для получения этого свойства непосредственно вызвать [CDaoDatabase::GetName](../../mfc/reference/cdaodatabase-class.md#getname). Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.  
  
 *m_bUpdatable*  
 Указывает, может ли внесены изменения в базу данных. Для получения этого свойства непосредственно вызвать [CDaoDatabase::CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate). Дополнительные сведения см. в разделе «Обновляемые свойства» в справке DAO.  
  
 *m_bTransactions*  
 Указывает, поддерживает ли источник данных транзакций — запись в ряд изменений, которые позже может быть выполнен откат (отменено) или фиксации (Сохранить). Если базы данных зависит от базы данных Microsoft Jet, имеет ненулевое значение свойства транзакций и транзакции можно использовать. Другие СУБД может не поддерживать транзакции. Для получения этого свойства непосредственно вызвать [CDaoDatabase::CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact). Дополнительные сведения см. в разделе «Свойство транзакции» в справке DAO.  
  
 *m_strVersion*  
 Указывает версию базы данных Microsoft Jet. Чтобы получить значение этого свойства напрямую, вызовите объекта базы данных [GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion) функции-члена. Дополнительные сведения см. в разделе «Версии свойство» в справке DAO.  
  
 *m_lCollatingOrder*  
 Задает последовательность порядка сортировки в текст для сравнения строк или сортировки. Возможные допустимые значения приведены ниже.  
  
- **dbSortGeneral** использовать общий порядок сортировки (английский, французский, немецкий, португальский, итальянский и современной).  
  
- **dbSortArabic** используется порядок сортировки для арабского языка.  
  
- **dbSortCyrillic** используется порядок сортировки русский.  
  
- **dbSortCzech** использовать чешский сортировку.  
  
- **dbSortDutch** использовать голландский сортировку.  
  
- **dbSortGreek** используется порядок сортировки греческого языка.  
  
- **dbSortHebrew** используется порядок сортировки иврита.  
  
- **dbSortHungarian** используется венгерская сортировку.  
  
- **dbSortIcelandic** использовать Исландский сортировку.  
  
- **dbSortNorwdan** используется порядок сортировки норвежский или датского языка.  
  
- **dbSortPDXIntl** используется порядок сортировки международной Paradox.  
  
- **dbSortPDXNor** использовать Paradox норвежский или порядок сортировки для датского языка.  
  
- **dbSortPDXSwe** использовать Paradox шведский или финский сортировку.  
  
- **dbSortPolish** использовать польский сортировку.  
  
- **dbSortSpanish** используется порядок сортировки.  
  
- **dbSortSwedFin** используется порядок сортировки шведский или финский.  
  
- **dbSortTurkish** используется порядок сортировки для турецкого языка.  
  
- **dbSortUndefined** порядок сортировки не определено или неизвестное.  
  
 Дополнительные сведения см. в разделе «Настройка Windows реестра параметры для доступа к данным» в справке DAO.  
  
 *m_nQueryTimeout*  
 Количество секунд ожидания базы данных Microsoft Jet, прежде чем выдать ошибку времени ожидания происходит при запуске запроса в базе данных ODBC. Значение времени ожидания по умолчанию — 60 секунд. Когда QueryTimeout имеет значение 0, происходит без времени ожидания; Это может привести к зависанию программы. Чтобы получить значение этого свойства напрямую, вызовите объекта базы данных [GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) функции-члена. Дополнительные сведения см. в разделе «QueryTimeout свойство» в справке DAO.  
  
 *m_strConnect*  
 Предоставляет сведения об источнике открытую базу данных. Для получения сведений о объединение строк и сведения о непосредственно получение значения данного свойства см. в разделе [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) функции-члена. Дополнительные сведения см. в разделе «Свойства подключения», справки DAO.  
  
## <a name="remarks"></a>Примечания  
 База данных находится базовый объект класса MFC объекта DAO [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md). Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются сведения по [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) функции-члена.  
  
 Сведений, получаемых методом [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) функции-члена хранится в `CDaoDatabaseInfo` структуры. Вызовите `GetDatabaseInfo` для `CDaoWorkspace` объекта в коллекции, баз данных хранится объект базы данных. `CDaoDatabaseInfo` также определяет `Dump` функции-члена в отладочных построений. Можно использовать `Dump` для помещения в дамп содержимого `CDaoDatabaseInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)   
 [Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)
