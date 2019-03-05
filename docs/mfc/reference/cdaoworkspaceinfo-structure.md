---
title: Структура CDaoWorkspaceInfo
ms.date: 11/04/2016
f1_keywords:
- CDaoWorkspaceInfo
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
ms.openlocfilehash: afbc73c079a6deec3f3e1b7455f9f2dbface5025
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271558"
---
# <a name="cdaoworkspaceinfo-structure"></a>Структура CDaoWorkspaceInfo

`CDaoWorkspaceInfo` Структура содержит сведения о рабочей области, определенные для доступа к базе данных объектов (DAO) доступа к данным.

## <a name="syntax"></a>Синтаксис

```
struct CDaoWorkspaceInfo
{
    CString m_strName;           // Primary
    CString m_strUserName;       // Secondary
    BOOL m_bIsolateODBCTrans;    // All
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Однозначно называет объект рабочей области. Чтобы получить значение этого свойства напрямую, вызовите объекта querydef [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) функция-член. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.

*m_strUserName*<br/>
Значение, представляющее владельца объекта рабочей области. Дополнительные сведения см. в разделе «Свойства UserName» в справке DAO.

*m_bIsolateODBCTrans*<br/>
Значение, указывающее, изолированы ли несколько транзакций с одной и той же базе данных ODBC. Дополнительные сведения см. в разделе [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans). Дополнительные сведения см. в разделе «IsolateODBCTrans свойство» в справке DAO.

## <a name="remarks"></a>Примечания

Рабочая область находится объект класса [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются данные по [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) функции-члена в классе `CDaoWorkspace`.

Сведений, получаемых методом [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) функция-член хранится в `CDaoWorkspaceInfo` структуры. `CDaoWorkspaceInfo` также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для помещения в дамп содержимое `CDaoWorkspaceInfo` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)
