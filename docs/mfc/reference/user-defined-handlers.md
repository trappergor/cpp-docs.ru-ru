---
title: Пользовательские обработчики | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.handlers
dev_langs:
- C++
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_MESSAGE macro [MFC]
- user-defined handlers [MFC]
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fdc8c70f7ef9bdd04bf40f408c4e014b3e3faa3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373250"
---
# <a name="user-defined-handlers"></a>Пользовательские обработчики
Следующие записи карты соответствуют прототипы функций.  
  
|Элемент карты|Прототип функции|  
|---------------|------------------------|  
|ON_MESSAGE ( \<сообщения >, \<memberFxn >)|memberFxn LRESULT afx_msg (WPARAM, LPARAM);|  
|ON_REGISTERED_MESSAGE ( \<nMessageVariable >, \<memberFxn >)|memberFxn LRESULT afx_msg (WPARAM, LPARAM);|  
|ON_THREAD_MESSAGE ( \<сообщения >, \<memberFxn >)|void memberFxn afx_msg (WPARAM, LPARAM);|  
|ON_REGISTERED_THREAD_MESSAGE ( \<nMessageVariable >, \<memberFxn >)|void memberFxn afx_msg (WPARAM, LPARAM);|  
  
## <a name="see-also"></a>См. также  
 [Схемы сообщений](../../mfc/reference/message-maps-mfc.md)   
 [Обработчики для сообщений WM_](../../mfc/reference/handlers-for-wm-messages.md)

