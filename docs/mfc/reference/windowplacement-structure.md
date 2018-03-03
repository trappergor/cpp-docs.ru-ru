---
title: "Структура WINDOWPLACEMENT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WINDOWPLACEMENT
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPLACEMENT structure [MFC]
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e73065cdf20d68b1da4ba77d1ad555e2bf95e937
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="windowplacement-structure"></a>Структура WINDOWPLACEMENT
`WINDOWPLACEMENT` Структура содержит сведения о размещении окна на экране**.**  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagWINDOWPLACEMENT {     /* wndpl */  
    UINT length;  
    UINT flags;  
    UINT showCmd;  
    POINT ptMinPosition;  
    POINT ptMaxPosition;  
    RECT rcNormalPosition;  
} WINDOWPLACEMENT;  
```  
  
#### <a name="parameters"></a>Параметры  
 *length*  
 Задает длину в байтах структуры**.**  
  
 `flags`  
 Задает флаги, определяющие положение свернутого окна, а также метод, с помощью которого восстанавливается окна. Этот член может быть один или оба из следующих флагов:  
  
- **WPF_SETMINPOSITION** указывает, что можно указать x - и y позиции свернутого окна**.** Этот флаг должен быть указан, если координаты задаются в **ptMinPosition** член.  
  
- **WPF_RESTORETOMAXIMIZED** указывает, что восстановленного окна будет развернуть, независимо от ли он было развернуто, прежде чем он был свернут. Этот параметр применим только при очередном окно восстановлено. Это не приводит к изменению восстановления поведения по умолчанию. Этот флаг доступен, только если **SW_SHOWMINIMIZED** задано значение для **showCmd** член.  
  
 *showCmd*  
 Указывает текущее состояние отображения окна. Этот член может принимать одно из следующих значений:  
  
- **SW_HIDE** скрывает окно и передает активации в другом окне.  
  
- **SW_MINIMIZE** сводит к минимуму указанного окна и активирует окно верхнего уровня в списке в системе.  
  
- **SW_RESTORE** активация и отображает окно. Если окно сворачивать или разворачивать, Windows восстанавливает его исходный размер и положение (то же, что **SW_SHOWNORMAL**).  
  
- **SW_SHOW** активирует окно и отображает его в его текущего размера и положения.  
  
- **SW_SHOWMAXIMIZED** активирует окно и отображает его в виде развернутого окна.  
  
- **SW_SHOWMINIMIZED** активирует окно и отображает его в виде значка.  
  
- **SW_SHOWMINNOACTIVE** отображает окно в виде значка. Окно, которое в данный момент активна остается активным.  
  
- **SW_SHOWNA** отображает окно в ее текущем состоянии. Окно, которое в данный момент активна остается активным.  
  
- **SW_SHOWNOACTIVATE** отображает окно в свои последние размер и положение. Окно, которое в данный момент активна остается активным.  
  
- **SW_SHOWNORMAL** активация и отображает окно. Если окно сворачивать или разворачивать, Windows восстанавливает его исходный размер и положение (то же, что **SW_RESTORE**).  
  
 *ptMinPosition*  
 Задает позицию верхнего левого угла окна при окно свернется.  
  
 `ptMaxPosition`  
 Задает позицию верхнего левого угла окна, если окно развернуто.  
  
 *rcNormalPosition*  
 Задает координаты окна, если это окно находится в нормальной позиции (восстановленные).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)

