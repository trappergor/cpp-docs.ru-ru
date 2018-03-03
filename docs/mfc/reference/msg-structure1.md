---
title: "MSG Structure1 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MSG
dev_langs:
- C++
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b504f116dcbff7fa45e741ff9715070ee0c74583
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="msg-structure1"></a>MSG Structure1
`MSG` Структура содержит сведения о сообщения из очереди сообщений потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagMSG {     // msg    
    HWND hwnd;  
    UINT message;  
    WPARAM wParam;  
    LPARAM lParam;  
    DWORD time;  
    POINT pt;  
} MSG;  
```  
  
#### <a name="parameters"></a>Параметры  
 *HWND*  
 Идентифицирует окно которого процедура окна получает сообщения.  
  
 `message`  
 Указывает номер сообщения.  
  
 `wParam`  
 Задает дополнительные сведения о сообщении. Точное значение зависит от значения **сообщение** член.  
  
 `lParam`  
 Задает дополнительные сведения о сообщении. Точное значение зависит от значения **сообщение** член.  
  
 `time`  
 Указывает время, когда сообщение отправлено.  
  
 `pt`  
 Задает положение курсора, в экранных координатах при передачи сообщения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

