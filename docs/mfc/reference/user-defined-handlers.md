---
title: "Пользовательские обработчики | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.handlers
dev_langs:
- C++
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro
- ON_MESSAGE macro
- user-defined handlers
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
caps.latest.revision: 10
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f0fc367bc19f0db23efddfc69fdeac519185ff0c
ms.lasthandoff: 02/24/2017

---
# <a name="user-defined-handlers"></a>Пользовательские обработчики
Следующие записи карты соответствуют прототипы функций.  
  
|Запись сопоставления|Прототип функции|  
|---------------|------------------------|  
|ON_MESSAGE ( \<сообщений настроек, \<memberFxn настроек)|memberFxn LRESULT afx_msg (WPARAM, LPARAM);|  
|ON_REGISTERED_MESSAGE ( \<nMessageVariable настроек, \<memberFxn настроек)|memberFxn LRESULT afx_msg (WPARAM, LPARAM);|  
|ON_THREAD_MESSAGE ( \<сообщений настроек, \<memberFxn настроек)|void memberFxn afx_msg (WPARAM, LPARAM);|  
|ON_REGISTERED_THREAD_MESSAGE ( \<nMessageVariable настроек, \<memberFxn настроек)|void memberFxn afx_msg (WPARAM, LPARAM);|  
  
## <a name="see-also"></a>См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)   
 [Обработчики для сообщений WM_](../../mfc/reference/handlers-for-wm-messages.md)


