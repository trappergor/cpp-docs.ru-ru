---
title: Структура CDaoRelationFieldInfo
ms.date: 11/04/2016
f1_keywords:
- CDaoRelationFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
ms.openlocfilehash: 9a00d1cbaf58729863a85d4e9053c9241e9566ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599411"
---
# <a name="cdaorelationfieldinfo-structure"></a>Структура CDaoRelationFieldInfo

`CDaoRelationFieldInfo` Структура содержит сведения о поле в связь, определенную для объектах доступа к данным (DAO).

## <a name="syntax"></a>Синтаксис

```
struct CDaoRelationFieldInfo
{
    CString m_strName;           // Primary
    CString m_strForeignName;    // Primary
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Имя поля в таблице первичного отношения.

*m_strForeignName*<br/>
Имя поля в таблице внешнего отношения.

## <a name="remarks"></a>Примечания

Объект связи DAO задает поля в основной таблицы и поля во внешней таблице, которые определяют связь. Ссылки на основной в определение структуры выше указывают, как информация возвращается в `m_pFieldInfos` членом [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) объекта, полученного путем вызова [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)функция-член класса `CDaoDatabase`.

Класс MFC не представленных отношения объектов и отношения объектов полей. Вместо этого DAO объекты базовых объектов MFC класса [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) содержать коллекцию объектов отношения, который называется коллекции отношений. Каждый объект отношения, в свою очередь, содержит коллекцию объектов field отношения. Каждый объект поля связь сопоставляет поля в таблице первичного с полем во внешней таблице. Взятые вместе, объекты поле отношений определить группу полей в каждой таблице, которые вместе образуют связь. `CDaoDatabase` предоставляет доступ к объекты отношений с `CDaoRelationInfo` путем вызова метода `GetRelationInfo` функция-член. `CDaoRelationInfo` Объекта, затем имеет член данных, `m_pFieldInfos`, который указывает на массив `CDaoRelationFieldInfo` объектов.

Вызовите [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) функция-член, содержащего `CDaoDatabase` объекта в объект отношения, которые вас интересуют, хранятся отношения является коллекция. Затем получить доступ к `m_pFieldInfos` членом [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) объекта. `CDaoRelationFieldInfo` также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для помещения в дамп содержимое `CDaoRelationFieldInfo` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Структура CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)
