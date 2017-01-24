---
title: "CDialogEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDialogEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogEx class"
  - "CDialogEx::PreTranslateMessage method"
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
caps.latest.revision: 27
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDialogEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CDialogEx` задает цвет фона и фоновое изображение для диалогового окна.  
  
## Синтаксис  
  
```  
class CDialogEx : public CDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDialogEx::CDialogEx](../Topic/CDialogEx::CDialogEx.md)|Создает объект `CDialogEx`.|  
|`CDialogEx::~CDialogEx`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDialogEx::SetBackgroundColor](../Topic/CDialogEx::SetBackgroundColor.md)|Задает цвет фона диалогового окна.|  
|[CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md)|Задает фоновое изображение диалогового окна.|  
  
## Заметки  
 Чтобы использовать класс `CDialogEx`, сформируйте класс диалогового окна из класса `CDialogEx` вместо класса `CDialog`.  
  
 Изображения диалогового окна хранятся в файле ресурсов.  Платформа автоматически удаляет все изображения, загруженные из файла ресурсов.  Чтобы программно удалить текущее фоновое изображение, вызовите метод [CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md) или реализуйте обработчик событий `OnDestroy`.  При вызове метода [CDialogEx::SetBackgroundImage](../Topic/CDialogEx::SetBackgroundImage.md) передайте параметр `HBITMAP` в качестве маркера изображения.  Объект `CDialogEx` будет распоряжаться изображением и может удалить его, если для флажка `m_bAutoDestroyBmp` установлено значение `TRUE`.  
  
 Объект `CDialogEx` может быть родительским элементом для объекта [CMFCPopupMenu Class](../Topic/CMFCPopupMenu%20Class.md).  Объект [CMFCPopupMenu Class](../Topic/CMFCPopupMenu%20Class.md) вызывает метод `CDialogEx::SetActiveMenu`, когда открывается объект [CMFCPopupMenu Class](../Topic/CMFCPopupMenu%20Class.md).  После этого объект `CDialogEx` обрабатывает любые события меню, пока объект [CMFCPopupMenu Class](../Topic/CMFCPopupMenu%20Class.md) не будет закрыт.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
## Требования  
 **Заголовок:** afxdialogex.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCPopupMenu Class](../Topic/CMFCPopupMenu%20Class.md)   
 [CContextMenuManager Class](../../mfc/reference/ccontextmenumanager-class.md)