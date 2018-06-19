---
title: MSG Structure1 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MSG
dev_langs:
- C++
helpviewer_keywords:
- MSG structure [MFC]
ms.assetid: dc166d27-9423-41f1-9599-5ba76d2f0138
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41dbbcdd3404705a9ac7c6c7969a9ebeeb0238f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372261"
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

