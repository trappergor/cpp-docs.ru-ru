---
title: Структура CDaoDatabaseInfo
ms.date: 09/17/2019
f1_keywords:
- CDaoDatabaseInfo
helpviewer_keywords:
- CDaoDatabaseInfo structure [MFC]
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
ms.openlocfilehash: 46d8056ee4ab478b65f3ef0bd59d88bd3af9b28c
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096159"
---
# <a name="cdaodatabaseinfo-structure"></a>Структура CDaoDatabaseInfo

`CDaoDatabaseInfo` Структура содержит сведения об объекте базы данных, определенном для объектов доступа к данным (DAO).
Версия DAO 3,6 является окончательной и считается устаревшей.

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
Уникально именует объект базы данных. Чтобы напрямую получить это свойство, вызовите [CDaoDatabase:: Name](../../mfc/reference/cdaodatabase-class.md#getname). Дополнительные сведения см. в разделе "свойство Name" справки DAO.

*m_bUpdatable*<br/>
Указывает, можно ли вносить изменения в базу данных. Чтобы напрямую получить это свойство, вызовите метод [CDaoDatabase:: канупдате](../../mfc/reference/cdaodatabase-class.md#canupdate). Дополнительные сведения см. в разделе "обновляемое свойство" справки DAO.

*m_bTransactions*<br/>
Указывает, поддерживает ли источник данных транзакции — запись ряда изменений, которые впоследствии можно откатить (отменить) или зафиксировать (сохранить). Если база данных основана на ядре СУБД Microsoft Jet, свойство Transactions не равно нулю и можно использовать транзакции. Другие ядра СУБД могут не поддерживать транзакции. Чтобы напрямую получить это свойство, вызовите метод [CDaoDatabase:: кантрансакт](../../mfc/reference/cdaodatabase-class.md#cantransact). Дополнительные сведения см. в разделе "свойства транзакций" справки DAO.

*m_strVersion*<br/>
Указывает версию ядра СУБД Microsoft Jet. Чтобы получить значение этого свойства напрямую, вызовите [функцию члена GetObject объекта базы](../../mfc/reference/cdaodatabase-class.md#getversion) данных. Дополнительные сведения см. в разделе "свойство Version" справки DAO.

*m_lCollatingOrder*<br/>
Задает последовательность порядка сортировки в тексте для сравнения строк или сортировки. Возможные значения:

- `dbSortGeneral`Используйте порядок сортировки "общий" (английский, французский, немецкий, португальский, итальянский и современный испанский).

- `dbSortArabic`Используйте порядок сортировки для арабского языка.

- `dbSortCyrillic`Используйте русский порядок сортировки.

- `dbSortCzech`Используйте чешский порядок сортировки.

- `dbSortDutch`Используйте Голландский порядок сортировки.

- `dbSortGreek`Используйте греческий порядок сортировки.

- `dbSortHebrew`Используйте порядок сортировки для иврита.

- `dbSortHungarian`Используйте Венгерский порядок сортировки.

- `dbSortIcelandic`Используйте порядок сортировки исландского.

- `dbSortNorwdan`Используйте норвежский или датский порядок сортировки.

- `dbSortPDXIntl`Используйте международный порядок сортировки Paradox.

- `dbSortPDXNor`Используйте порядок сортировки Paradox норвежский или датский.

- `dbSortPDXSwe`Используйте порядок сортировки Paradox шведский или финский.

- `dbSortPolish`Используйте польский порядок сортировки.

- `dbSortSpanish`Используйте испанский порядок сортировки.

- `dbSortSwedFin`Используйте шведский или Финский порядок сортировки.

- `dbSortTurkish`Используйте порядок сортировки для турецкого языка.

- `dbSortUndefined`Порядок сортировки не определен или неизвестен.

Дополнительные сведения см. в разделе «Настройка параметров реестра Windows для доступа к данным» справки DAO.

*m_nQueryTimeout*<br/>
Количество секунд, в течение которых ядро СУБД Microsoft Jet ждет возникновения ошибки времени ожидания при выполнении запроса в базе данных ODBC. Значение времени ожидания по умолчанию — 60 секунд. Когда параметр QueryTimeout имеет значение 0, время ожидания не возникает; Это может привести к тому, что программа перестает отвечать на запросы. Чтобы получить значение этого свойства напрямую, вызовите функцию члена [GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout) объекта базы данных. Дополнительные сведения см. в разделе "свойство QueryTimeout" справки DAO.

*m_strConnect*<br/>
Предоставляет сведения об источнике открытой базы данных. Сведения о строках соединения и сведения о получении значения этого свойства напрямую см. в описании функции члена [CDaoDatabase::](../../mfc/reference/cdaodatabase-class.md#getconnect) . Дополнительные сведения см. в подразделе «свойство Connect» справки DAO.

## <a name="remarks"></a>Примечания

База данных — это объект DAO, лежащий в основе объекта MFC класса [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md). Ссылки на первичный, вторичный и все вышеперечисленное указывают, как эта информация возвращается функцией-членом [кдаоворкспаце:: жетдатабасеинфо](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) .

Сведения, получаемые функцией-членом [кдаоворкспаце:: жетдатабасеинфо](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo) , хранятся `CDaoDatabaseInfo` в структуре. Вызовите `GetDatabaseInfo` метод `CDaoWorkspace` для объекта, в коллекции баз данных которого хранится объект базы данных. `CDaoDatabaseInfo`также определяет функцию `Dump` -член в отладочных сборках. Можно использовать `Dump` для дампа содержимого `CDaoDatabaseInfo` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** афксдао. h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)<br/>
[Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)
