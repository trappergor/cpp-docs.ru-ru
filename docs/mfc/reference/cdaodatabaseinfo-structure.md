---
title: Структура CDaoDatabaseInfo
ms.date: 11/04/2016
f1_keywords:
- CDaoDatabaseInfo
helpviewer_keywords:
- CDaoDatabaseInfo structure [MFC]
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
ms.openlocfilehash: 920301af6f660aeac010ecbf844b80ea628bbfd7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285637"
---
# <a name="cdaodatabaseinfo-structure"></a>Структура CDaoDatabaseInfo

`CDaoDatabaseInfo` Структура содержит сведения об объекте базы данных, определенных для объектах доступа к данным (DAO).

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

*m_strName*<br/>
Однозначно называет объект базы данных. Чтобы получить это свойство напрямую вызвать [CDaoDatabase::GetName](../../mfc/reference/cdaodatabase-class.md#getname). Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.

*m_bUpdatable*<br/>
Указывает, можно ли сделать изменения в базу данных. Чтобы получить это свойство напрямую вызвать [CDaoDatabase::CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate). Дополнительные сведения см. в разделе «Обновляемые свойство» в справке DAO.

*m_bTransactions*<br/>
Указывает, поддерживает ли источник данных транзакций — запись ряд изменений, которые можно позднее выполнить откат (отменено) или фиксации (Сохранить). Если базы данных зависит от базы данных Microsoft Jet, свойство транзакции не равно нулю, и транзакции можно использовать. Другие ядра СУБД может не поддерживать транзакции. Чтобы получить это свойство напрямую вызвать [CDaoDatabase::CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact). Дополнительные сведения см. в разделе «Транзакции свойство» в справке DAO.

*m_strVersion*<br/>
Указывает номер версии базы данных Microsoft Jet. Чтобы получить значение этого свойства напрямую, вызовите объект базы данных [GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion) функция-член. Дополнительные сведения см. в разделе «Свойство Version» в справке DAO.

*m_lCollatingOrder*<br/>
Указывает последовательность сортировки в текст для сравнения строк или сортировки. Возможные значения:

- `dbSortGeneral` Используйте общий порядок сортировки (английский, французский, немецкий, португальский, итальянский и современных испанский).

- `dbSortArabic` Использует порядок сортировки для арабского языка.

- `dbSortCyrillic` Используйте порядок сортировки русский.

- `dbSortCzech` Используйте чешский сортировку.

- `dbSortDutch` Используйте голландский сортировку.

- `dbSortGreek` Используйте греческие сортировку.

- `dbSortHebrew` Используйте порядок сортировки иврита.

- `dbSortHungarian` Используйте венгерская сортировку.

- `dbSortIcelandic` Используйте Icelandic сортировку.

- `dbSortNorwdan` Используйте порядок сортировки норвежская или датского языка.

- `dbSortPDXIntl` Используйте порядок сортировки международных Paradox.

- `dbSortPDXNor` Используйте для Paradox норвежская или порядок сортировки для датского языка.

- `dbSortPDXSwe` Используйте для Paradox шведский или финский сортировку.

- `dbSortPolish` Используйте польский сортировку.

- `dbSortSpanish` Использует порядок сортировки.

- `dbSortSwedFin` Используйте порядок сортировки на шведский или финский.

- `dbSortTurkish` Используйте из турецкого порядка сортировки.

- `dbSortUndefined` Порядок сортировки является неопределенным или неизвестен.

Дополнительные сведения см. в разделе «Настройка Windows реестра параметры для доступа к данным» в справке DAO.

*m_nQueryTimeout*<br/>
Количество секунд ожидания ядра СУБД Microsoft Jet, прежде чем выдать ошибку времени ожидания происходит, когда запрос выполняется в базе данных ODBC. По умолчанию время ожидания составляет 60 секунд. Когда QueryTimeout имеет значение 0, время ожидания не происходит; Это может привести к зависанию программы. Чтобы получить значение этого свойства напрямую, вызовите объект базы данных [GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) функция-член. Дополнительные сведения см. в разделе «QueryTimeout свойство» в справке DAO.

*m_strConnect*<br/>
Сведения об источнике открытую базу данных. Сведения о объединение строк и сведения о получении значения этого свойства напрямую, см. в разделе [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect) функция-член. Дополнительные сведения см. в разделе «Свойства подключения», в справке DAO.

## <a name="remarks"></a>Примечания

Базы данных является объектом DAO, базовый объект класса MFC [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md). Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются данные по [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) функция-член.

Сведений, получаемых методом [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) функция-член хранится в `CDaoDatabaseInfo` структуры. Вызовите `GetDatabaseInfo` для `CDaoWorkspace` объекта, в которых коллекции баз данных хранится объект базы данных. `CDaoDatabaseInfo` также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для помещения в дамп содержимое `CDaoDatabaseInfo` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)<br/>
[Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)
