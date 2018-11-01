---
title: Структура CDaoIndexFieldInfo
ms.date: 11/04/2016
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: 358e6654060e92e0df83b118fa70e1c3a3a990b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449586"
---
# <a name="cdaoindexfieldinfo-structure"></a>Структура CDaoIndexFieldInfo

`CDaoIndexFieldInfo` Структура содержит сведения об объекте индекс поля, определенные для объектах доступа к данным (DAO).

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
Однозначно называет объект поля индекса. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.

*m_bDescending*<br/>
Указывает, упорядочение индекс, определенный объектом index. Значение TRUE, если по убыванию.

## <a name="remarks"></a>Примечания

Объект индекса, может иметь несколько полей, указывающее, какие поля на индексируется tabledef (или набор записей на основе таблицы). Ссылки на основной выше указывают, как информация возвращается в `m_pFieldInfos` членом [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) объекта, полученного путем вызова `GetIndexInfo` функция-член класса [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).

Класс MFC не представленных объектов индекса и объектов индекса поля. Вместо этого DAO объекты базовых объектов MFC класса [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) или [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) содержать коллекцию объектов индекса, который называется коллекцию индексов. Каждый объект индекса, в свою очередь, содержит коллекцию объектов полей. Эти классы предоставлять функции-члены для доступа к отдельным элементам данных индекса, или использовать их все одновременно с `CDaoIndexInfo` путем вызова метода `GetIndexInfo` функция-член края содержащего его объекта. `CDaoIndexInfo` Объекта, затем имеет член данных, `m_pFieldInfos`, который указывает на массив `CDaoIndexFieldInfo` объектов.

Вызовите `GetIndexInfo` функция-член от содержащего объекта tabledef или набора записей, в которых индексы — коллекции хранятся объект индекса, которые вас интересуют. Затем получить доступ к `m_pFieldInfos` членом [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) объекта. Длина `m_pFieldInfos` массив хранится в `m_nFields`. `CDaoIndexFieldInfo` также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для помещения в дамп содержимое `CDaoIndexFieldInfo` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)

