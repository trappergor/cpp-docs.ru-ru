---
title: "Структура WINDOWPLACEMENT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WINDOWPLACEMENT
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPLACEMENT structure
ms.assetid: ea7d61f6-eb57-478e-9b08-7c1d07091aa8
caps.latest.revision: 11
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 62cf7003f43d50d5998dd527ae5ad7b10ab95686
ms.lasthandoff: 02/24/2017

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
 Указывает длину в байтах структуры**.**  
  
 `flags`  
 Задает флаги, определяющие положение свернутого окна, а также метод, по которому окно восстановлено. Этот член может быть одно или оба следующие флаги:  
  
- **WPF_SETMINPOSITION** указывает, что можно указать x - и y позиции свернутого окна**.** Этот флаг должен быть указан, если координаты задаются **ptMinPosition** член.  
  
- **WPF_RESTORETOMAXIMIZED** указывает, что восстановленного окна будет развернуть, вне зависимости от того, было ли оно было максимальным, прежде чем оно было свернуто. Этот параметр применим только при очередном окно восстановлено. Он не изменяет поведения восстановления по умолчанию. Этот флаг доступен, только если **SW_SHOWMINIMIZED** указано значение для **showCmd** член.  
  
 *showCmd*  
 Указывает текущее состояние отображения окна. Этот член может принимать одно из следующих значений:  
  
- **SW_HIDE** скрывает окно и передает активации в другом окне.  
  
- **SW_MINIMIZE** сводит к минимуму указанного окна и активирует окно верхнего уровня в списке системы.  
  
- **SW_RESTORE** активация и появится окно. Если окно свернуто или развернуто, Windows восстанавливает его исходный размер и положение (то же, что **SW_SHOWNORMAL**).  
  
- **SW_SHOW** активирует окно и отображает его в его текущего размера и положения.  
  
- **SW_SHOWMAXIMIZED** активирует окно и отображает его в виде развернутого окна.  
  
- **SW_SHOWMINIMIZED** активирует окно и отображает его в виде значка.  
  
- **SW_SHOWMINNOACTIVE** отображает окно, в виде значка. Окно активного остается активным.  
  
- **SW_SHOWNA** отображает окно в ее текущем состоянии. Окно активного остается активным.  
  
- **SW_SHOWNOACTIVATE** отображает окно в свои последние размер и положение. Окно активного остается активным.  
  
- **SW_SHOWNORMAL** активация и появится окно. Если окно свернуто или развернуто, Windows восстанавливает его исходный размер и положение (то же, что **SW_RESTORE**).  
  
 *ptMinPosition*  
 Задает позицию верхнего левого угла окна свернутое окно.  
  
 `ptMaxPosition`  
 Задает положение верхнего левого угла окна, если окно развернуто.  
  
 *rcNormalPosition*  
 Задает координаты окна, когда окно находится в нормальной позиции (восстановленные).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winuser.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::SetWindowPlacement](../../mfc/reference/cwnd-class.md#setwindowplacement)


