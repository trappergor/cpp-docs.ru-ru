---
title: "Класс CHwndRenderTarget | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHwndRenderTarget"
  - "afxrendertarget/CHwndRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHwndRenderTarget - класс"
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс CHwndRenderTarget
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для ID2D1HwndRenderTarget.  
  
## Синтаксис  
  
```  
class CHwndRenderTarget : public CRenderTarget;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHwndRenderTarget::CHwndRenderTarget](../Topic/CHwndRenderTarget::CHwndRenderTarget.md)|Создает объект CHwndRenderTarget из HWND.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHwndRenderTarget::Attach](../Topic/CHwndRenderTarget::Attach.md)|Присоединяет интерфейс существующего целевого буфера визуализации к объекту|  
|[CHwndRenderTarget::CheckWindowState](../Topic/CHwndRenderTarget::CheckWindowState.md)|Указывает, является ли связанный с этим целевым буфером визуализации дескриптор окна \(HWND\) закрытым.|  
|[CHwndRenderTarget::Create](../Topic/CHwndRenderTarget::Create.md)|Создает целевой буфер визуализации, связанный с окном.|  
|[CHwndRenderTarget::Detach](../Topic/CHwndRenderTarget::Detach.md)|Отсоединяет интерфейс целевого буфера визуализации от объекта|  
|[CHwndRenderTarget::GetHwnd](../Topic/CHwndRenderTarget::GetHwnd.md)|Возвращает дескриптор окна \(HWND\), связанный с данным целевым буфером визуализации.|  
|[CHwndRenderTarget::GetHwndRenderTarget](../Topic/CHwndRenderTarget::GetHwndRenderTarget.md)|Возвращает интерфейс ID2D1HwndRenderTarget.|  
|[CHwndRenderTarget::ReCreate](../Topic/CHwndRenderTarget::ReCreate.md)|Повторно создает целевой буфер визуализации, связанный с окном.|  
|[CHwndRenderTarget::Resize](../Topic/CHwndRenderTarget::Resize.md)|Изменяет размер целевого буфера визуализации до заданного размера в пикселях|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget\*](../Topic/CHwndRenderTarget::operator%20ID2D1HwndRenderTarget*.md)|Возвращает интерфейс ID2D1HwndRenderTarget.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CHwndRenderTarget::m\_pHwndRenderTarget](../Topic/CHwndRenderTarget::m_pHwndRenderTarget.md)|Указатель на объект ID2D1HwndRenderTarget.|  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)