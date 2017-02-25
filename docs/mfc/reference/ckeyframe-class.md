---
title: "Класс CKeyFrame | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CKeyFrame"
  - "CKeyFrame"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CKeyFrame - класс"
ms.assetid: d050a562-20f6-4c65-8ce5-ccb3aef1a20e
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Класс CKeyFrame
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет ключевой кадр анимации.  
  
## Синтаксис  
  
```  
class CKeyFrame : public CBaseKeyFrame;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CKeyFrame::CKeyFrame](../Topic/CKeyFrame::CKeyFrame.md)|Перегружен.  Создает опорный кадр, зависящий от другого опорного кадра.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CKeyFrame::AddToStoryboard](../Topic/CKeyFrame::AddToStoryboard.md)|Добавляет опорный кадр в раскадровку.  \(Переопределяет [CBaseKeyFrame::AddToStoryboard](../Topic/CBaseKeyFrame::AddToStoryboard.md).\)|  
|[CKeyFrame::AddToStoryboardAfterTransition](../Topic/CKeyFrame::AddToStoryboardAfterTransition.md)|Добавляет опорный кадр в раскадровку после перехода.|  
|[CKeyFrame::AddToStoryboardAtOffset](../Topic/CKeyFrame::AddToStoryboardAtOffset.md)|Добавляет опорный кадр в раскадровку со смещением.|  
|[CKeyFrame::GetExistingKeyframe](../Topic/CKeyFrame::GetExistingKeyframe.md)|Возвращает указатель на опорный кадр, от которого зависит данный опорный кадр.|  
|[CKeyFrame::GetOffset](../Topic/CKeyFrame::GetOffset.md)|Возвращает смещение относительно другого опорного кадра.|  
|[CKeyFrame::GetTransition](../Topic/CKeyFrame::GetTransition.md)|Возвращает указатель на переход, от которого зависит данный опорный кадр.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CKeyFrame::m\_offset](../Topic/CKeyFrame::m_offset.md)|Задает смещение данного опорного кадра относительно опорного кадра, хранящегося в m\_pExistingKeyFrame.|  
|[CKeyFrame::m\_pExistingKeyFrame](../Topic/CKeyFrame::m_pExistingKeyFrame.md)|Хранит указатель на существующий опорный кадр.  Этот опорный кадр добавляется в раскадровку со смещением относительно существующего опорного кадра, равным m\_offset.|  
|[CKeyFrame::m\_pTransition](../Topic/CKeyFrame::m_pTransition.md)|Хранит указатель на переход, который начинается на данном опорном кадре.|  
  
## Заметки  
 Этот класс реализует опорный кадр анимации.  Опорный кадр представляет момент времени внутри раскадровки и может использоваться для задания времени начала и окончания переходов.  Опорный кадр может быть основан на другом опорном кадре и иметь смещение \(в секундах\) относительно него, или может быть основан на переходе и представлять момент времени, соответствующий окончанию перехода.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CBaseKeyFrame](../Topic/CBaseKeyFrame%20Class.md)  
  
 [CKeyFrame](../../mfc/reference/ckeyframe-class.md)  
  
## Требования  
 **Заголовок:** afxanimationcontroller.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)