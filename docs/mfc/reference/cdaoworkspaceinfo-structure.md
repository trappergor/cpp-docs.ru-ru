---
title: Структура CDaoWorkspaceInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoWorkspaceInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 705c855a817f0c6ca342e51258c7d6c1e61fa392
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951082"
---
# <a name="cdaoworkspaceinfo-structure"></a>Структура CDaoWorkspaceInfo
`CDaoWorkspaceInfo` Структура содержит сведения о рабочей области, определенные для доступа к базе данных объекты (DAO) доступа к данным.  
  
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
 *m_strName*  
 Однозначно называет объект рабочей области. Чтобы получить значение этого свойства напрямую, вызовите объекта querydef [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) функции-члена. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.  
  
 *m_strUserName*  
 Значение, представляющее владельца объекта рабочей области. Дополнительные сведения см. в разделе «Свойство имени пользователя» справки DAO.  
  
 *m_bIsolateODBCTrans*  
 Значение, указывающее, изолированных ли несколько транзакций с одной и той же базе данных ODBC. Дополнительные сведения см. в разделе [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans). Дополнительные сведения см. в разделе «Свойство IsolateODBCTrans» в справке DAO.  
  
## <a name="remarks"></a>Примечания  
 Рабочая область — объект класса [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются сведения по [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) функции-члена в классе `CDaoWorkspace`.  
  
 Сведений, получаемых методом [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) функции-члена хранится в `CDaoWorkspaceInfo` структуры. `CDaoWorkspaceInfo` также определяет `Dump` функции-члена в отладочных построений. Можно использовать `Dump` для помещения в дамп содержимого `CDaoWorkspaceInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)
