---
title: "Класс CDCRenderTarget | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CDCRenderTarget"
  - "CDCRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDCRenderTarget - класс"
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Класс CDCRenderTarget
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Оболочка для ID2D1DCRenderTarget.  
  
## Синтаксис  
  
```  
class CDCRenderTarget : public CRenderTarget;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDCRenderTarget::CDCRenderTarget](../Topic/CDCRenderTarget::CDCRenderTarget.md)|Создает объект CDCRenderTarget.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDCRenderTarget::Attach](../Topic/CDCRenderTarget::Attach.md)|Присоединяет интерфейс существующего целевого буфера визуализации к объекту|  
|[CDCRenderTarget::BindDC](../Topic/CDCRenderTarget::BindDC.md)|Связывает целевой буфер визуализации с контекстом устройства, которому отдаются команды рисования|  
|[CDCRenderTarget::Create](../Topic/CDCRenderTarget::Create.md)|Создает объект CDCRenderTarget.|  
|[CDCRenderTarget::Detach](../Topic/CDCRenderTarget::Detach.md)|Отсоединяет интерфейс целевого буфера визуализации от объекта|  
|[CDCRenderTarget::GetDCRenderTarget](../Topic/CDCRenderTarget::GetDCRenderTarget.md)|Возвращает интерфейс ID2D1DCRenderTarget|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDCRenderTarget::operator ID2D1DCRenderTarget\*](../Topic/CDCRenderTarget::operator%20ID2D1DCRenderTarget*.md)|Возвращает интерфейс ID2D1DCRenderTarget|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CDCRenderTarget::m\_pDCRenderTarget](../Topic/CDCRenderTarget::m_pDCRenderTarget.md)|Указатель на объект ID2D1DCRenderTarget.|  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)  
  
## Требования  
 **Заголовок:** afxrendertarget.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)