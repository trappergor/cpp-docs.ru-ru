---
title: Структура CDaoIndexFieldInfo
ms.date: 09/17/2019
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: a8b0ff991b8cc4988192b89d7f70309af9b9112a
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096096"
---
# <a name="cdaoindexfieldinfo-structure"></a>Структура CDaoIndexFieldInfo

`CDaoIndexFieldInfo` Структура содержит сведения об объекте поля индекса, определенном для объектов доступа к данным (DAO).

DAO поддерживается в Office 2013. Версия DAO 3,6 является окончательной и считается устаревшей.

## <a name="syntax"></a>Синтаксис

```
struct CDaoIndexFieldInfo
{
    CString m_strName;          // Primary
    BOOL m_bDescending;         // Primary
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Уникально именует объект поля индекса. Дополнительные сведения см. в разделе "свойство Name" справки DAO.

*m_bDescending*<br/>
Указывает порядок индексов, определенный объектом index. Значение TRUE, если порядок сортировки по убыванию.

## <a name="remarks"></a>Примечания

Объект индекса может иметь несколько полей, указывающих, в каких полях будет индексироваться объект tabledef (или набор записей, основанный на таблице). Ссылки на `m_pFieldInfos` приведенный выше источник указывают, как данные возвращаются в элементе объекта [кдаоиндексинфо](../../mfc/reference/cdaoindexinfo-structure.md) , `GetIndexInfo` полученного путем вызова функции-члена класса [кдаотабледеф](../../mfc/reference/cdaotabledef-class.md#getindexinfo) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).

Объекты индекса и объекты полей индекса не представлены классом MFC. Вместо этого объекты DAO базовых объектов MFC класса [кдаотабледеф](../../mfc/reference/cdaotabledef-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) содержат коллекцию объектов index, называемую коллекцией индексов. Каждый объект индекса, в свою очередь, содержит коллекцию объектов Field. Эти классы предоставляют функции-члены для доступа к отдельным элементам сведений об индексах или для доступа к ним с помощью `CDaoIndexInfo` объекта путем `GetIndexInfo` вызова функции-члена содержащего его объекта. Затем объект содержит `m_pFieldInfos`элемент данных, `CDaoIndexFieldInfo` указывающий на массив объектов. `CDaoIndexInfo`

Вызовите функцию-член содержащего объекта tabledef или Recordset, в коллекции индексов которого хранится объект индекса, который вас интересует. `GetIndexInfo` Затем получите доступ `m_pFieldInfos` к члену объекта [кдаоиндексинфо](../../mfc/reference/cdaoindexinfo-structure.md) . Длина `m_pFieldInfos` массива хранится в `m_nFields`. `CDaoIndexFieldInfo`также определяет функцию `Dump` -член в отладочных сборках. Можно использовать `Dump` для дампа содержимого `CDaoIndexFieldInfo` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** афксдао. h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset:: Жетиндексинфо](../../mfc/reference/cdaorecordset-class.md#getindexinfo)
