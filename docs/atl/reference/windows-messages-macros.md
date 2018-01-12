---
title: "Макросы сообщений Windows | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: atlbase/ATL::WM_FORWARDMSG
dev_langs: C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6dde3255997b03eb827ef9e318de73b3badee23c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="windows-messages-macros"></a>Макросы сообщений Windows
Этот макрос пересылает сообщения окна.  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|Используйте для пересылки сообщений, полученных в окне другого окна для обработки.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h 
   
##  <a name="wm_forwardmsg"></a>WM_FORWARDMSG  
 Этот макрос пересылает сообщение, полученное в окне другого окна для обработки.  
  
```
WM_FORWARDMSG
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если сообщение было обработано, ноль, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Используйте `WM_FORWARDMSG` на пересылку сообщений, полученных в окне другого окна для обработки. Параметры LPARAM и WPARAM используются следующим образом:  
  
|Параметр|Использование|  
|---------------|-----------|  
|WPARAM|Данные, определенные пользователем|  
|LPARAM|Указатель на `MSG` структуру, содержащую сведения о сообщении|  
  
### <a name="example"></a>Пример  
 В следующем примере `m_hWndOther` представляет окно, получает это сообщение.  
  
 [!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)
