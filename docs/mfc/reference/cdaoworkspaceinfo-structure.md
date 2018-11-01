---
title: Структура CDaoWorkspaceInfo
ms.date: 11/04/2016
f1_keywords:
- CDaoWorkspaceInfo
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
ms.openlocfilehash: e47df7323d130bee2a378a4cf7dcae8001641f6e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562816"
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
