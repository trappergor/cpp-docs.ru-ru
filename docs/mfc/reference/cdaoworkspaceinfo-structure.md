---
title: "Структура CDaoWorkspaceInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoWorkspaceInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoWorkspaceInfo structure
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
caps.latest.revision: 13
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
ms.openlocfilehash: 44c1ce365a1eecdb2a500998c082c6a9245dffb2
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoworkspaceinfo-structure"></a>Структура CDaoWorkspaceInfo
`CDaoWorkspaceInfo` Структура содержит сведения о рабочей области, определенные для доступа к базе данных данные доступа объекты (DAO).  
  
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
 `m_strName`  
 Дает уникальное название объекта workspace. Чтобы получить значение этого свойства напрямую, вызовите объекта querydef [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) функции-члена. Дополнительные сведения см. в разделе «Свойства Name» в справке DAO.  
  
 *m_strUserName*  
 Значение, представляющее владельца объекта workspace. Дополнительные сведения см. в разделе «Свойства пользователя» в справке DAO.  
  
 *m_bIsolateODBCTrans*  
 Значение, указывающее, изолированное ли несколько транзакций с одной и той же базе данных ODBC. Дополнительные сведения см. в разделе [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans). Дополнительные сведения см. в разделе «IsolateODBCTrans свойство» в справке DAO.  
  
## <a name="remarks"></a>Примечания  
 Рабочая область находится объект класса [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Ссылки на основной, дополнительный и все указанные выше указывают, как возвращаются сведения по [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) функции-члена в классе `CDaoWorkspace`.  
  
 Данные, полученные по [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) функции-члена хранится в `CDaoWorkspaceInfo` структуру. `CDaoWorkspaceInfo`также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для вывода содержимого из `CDaoWorkspaceInfo` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdao.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Класс CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)

