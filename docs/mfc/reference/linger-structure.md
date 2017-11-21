---
title: "Структура LINGER | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LINGER
dev_langs: C++
helpviewer_keywords: LINGER structure [MFC]
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d1436c64cb7ec5a7d321e6e7fef5c76838842037
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="linger-structure"></a>Структура LINGER
`LINGER` Структура используется для управления **SO_LINGER** и **SO_DONTLINGER** параметры `CAsyncSocket::GetSockOpt`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct linger {  
    u_short l_onoff;            // option on/off  
    u_short l_linger;           // linger time  
};  
```  
  
## <a name="remarks"></a>Примечания  
 Установка **SO_DONTLINGER** отменяет блокирование функции-члена **закрыть** при ожидании неотправленные данные для отправки. Установка этого параметра эквивалентно заданию для **SO_LINGER** с **l_onoff** присвоено значение 0.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winsock2.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)   
 [CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)

