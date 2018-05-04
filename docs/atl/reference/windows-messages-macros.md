---
title: Макросы сообщений Windows | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
dev_langs:
- C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21bb273b94f871e253ab927238c96256f46e2b3a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="windows-messages-macros"></a>Макросы сообщений Windows
Этот макрос пересылает сообщения окна.  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|Используйте для пересылки сообщений, полученных в окне другого окна для обработки.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h 
   
##  <a name="wm_forwardmsg"></a>  WM_FORWARDMSG  
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
