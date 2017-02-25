---
title: "CSimpleDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CSimpleDialog"
  - "CSimpleDialgo"
  - "CSimpleDialog"
  - "ATL.CSimpleDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleDialog class"
  - "CSimpleDialog class, modal dialog boxes in ATL"
  - "диалоговые окна, модальные"
  - "модальные диалоговые окна, ATL - библиотека"
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSimpleDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует узел модальное диалоговое окно.  
  
## Синтаксис  
  
```  
  
      template <  
   WORD t_wDlgTemplateID,  
   BOOL t_bCenter = TRUE  
>  
class CSimpleDialog :  
   public CDialogImplBase  
```  
  
#### Параметры  
 *t\_wDlgTemplateID*  
  
 Идентификатор ресурса \(uri ресурса шаблона диалогового окна.  
  
 *t\_bCenter*  
 Если объект **TRUE** диалогового окна быть центризованным в поле "Владелец"; в противном случае **FALSE**.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleDialog::DoModal](../Topic/CSimpleDialog::DoModal.md)|Создание модального диалогового окна.|  
  
## Заметки  
 Реализует модального диалогового окна с базовой функциональностью.  `CSimpleDialog` обеспечивает поддержку управления Windows общих только для чтения.  Для создания и отображения модального диалогового окна, создайте экземпляр данного класса, подавая имя существующего шаблона ресурса для диалогового окна.  Объект диалогового окна, когда пользователь щелкает закрывает любой элемент управления со стандартным значением \(как IDOK или IDCANCEL\).  
  
 `CSimpleDialog` позволяет создать только модальные диалоговые окна.  `CSimpleDialog` предоставляет процедуру диалогового окна, которая по умолчанию использует сопоставление сообщения для направления сообщений к соответствующим обработчикам.  
  
 Дополнительные сведения см. в разделе [Реализация диалоговое окно](../../atl/implementing-a-dialog-box.md).  
  
## Иерархия наследования  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## Требования  
 **Header:**  atlwin.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)