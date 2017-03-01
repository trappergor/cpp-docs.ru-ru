---
title: "Макросы сообщений Windows | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
caps.latest.revision: 16
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: be814c0a2ade7df8f7a4d6863627e79efe0a48bc
ms.lasthandoff: 02/24/2017

---
# <a name="windows-messages-macros"></a>Макросы сообщений Windows
Этот макрос пересылает сообщения окна.  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|Используйте для пересылки полученных окна в другое окно для обработки сообщения.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h 
   
##  <a name="a-namewmforwardmsga--wmforwardmsg"></a><a name="wm_forwardmsg"></a>WM_FORWARDMSG  
 Этот макрос пересылает сообщение, полученное в окне другого окна для обработки.  
  
```
WM_FORWARDMSG
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение было обработано, ноль, если не.  
  
### <a name="remarks"></a>Примечания  
 Используйте `WM_FORWARDMSG` для пересылки полученных окна в другое окно для обработки сообщения. Параметры LPARAM и WPARAM используются следующим образом:  
  
|Параметр|Использование|  
|---------------|-----------|  
|WPARAM|Данные, определенные пользователем|  
|LPARAM|Указатель на `MSG` структуру, содержащую сведения о сообщении|  
  
### <a name="example"></a>Пример  
 В следующем примере `m_hWndOther` представляет окно, которое получает сообщение.  
  
 [!code-cpp[NVC_ATL_Windowing&#137;](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)

