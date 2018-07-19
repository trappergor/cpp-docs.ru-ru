---
title: MSG Structure1 | Документация Майкрософт
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
ms.openlocfilehash: 5fe629c2f279b6b258f4824229490f7b72b4ce4d
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37338816"
---
# <a name="msg-structure1"></a>MSG Structure1
`MSG` Структура содержит информацию сообщения из очереди сообщений потока.  
  
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
 Идентифицирует окна, Оконная процедура которого получает сообщение.  
  
 *message*  
 Указывает номер сообщения.  
  
 *wParam*  
 Задает дополнительные сведения о сообщении. Точный смысл зависит от значения `message` член.  
  
 *lParam*  
 Задает дополнительные сведения о сообщении. Точный смысл зависит от значения `message` член.  
  
 *time*  
 Указывает время, по которому было сгенерировано сообщение.  
  
 *pt*  
 Указывает положение курсора в экранных координатах, когда было сгенерировано сообщение.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

