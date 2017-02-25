---
title: "CSnapInPropertyPageImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSnapInPropertyPageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSnapInPropertyPageImpl class"
  - "страницы свойств, ATL - библиотека"
  - "snap-ins"
  - "snap-ins, страницы свойств"
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSnapInPropertyPageImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для реализации объект страницы свойств оснастки.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
CSnapInPropertyPageImpl : public CDialogImplBase  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](../Topic/CSnapInPropertyPageImpl::CSnapInPropertyPageImpl.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSnapInPropertyPageImpl::CancelToClose](../Topic/CSnapInPropertyPageImpl::CancelToClose.md)|Изменяет состояние кнопки **ОК** и **Отмена**.|  
|[CSnapInPropertyPageImpl::Create](../Topic/CSnapInPropertyPageImpl::Create.md)|Инициализирует только что созданный объект `CSnapInPropertyPageImpl`.|  
|[CSnapInPropertyPageImpl::OnApply](../Topic/CSnapInPropertyPageImpl::OnApply.md)|Вызываемый платформой, когда пользователь нажимает кнопку **Применить** при использовании страницу свойств мастер\- типа.|  
|[CSnapInPropertyPageImpl::OnHelp](../Topic/CSnapInPropertyPageImpl::OnHelp.md)|Вызываемый платформой, когда пользователь нажимает кнопку **Справка** при использовании страницу свойств мастер\- типа.|  
|[CSnapInPropertyPageImpl::OnKillActive](../Topic/CSnapInPropertyPageImpl::OnKillActive.md)|Вызываемый платформой, если текущая страница больше не активна.|  
|[CSnapInPropertyPageImpl::OnQueryCancel](../Topic/CSnapInPropertyPageImpl::OnQueryCancel.md)|Вызываемый платформой, когда пользователь нажимает кнопку **Отмена** и до отмены осуществляло.|  
|[CSnapInPropertyPageImpl::OnReset](../Topic/CSnapInPropertyPageImpl::OnReset.md)|Вызываемый платформой, когда пользователь нажимает кнопку **Сброс** при использовании страницу свойств мастер\- типа.|  
|[CSnapInPropertyPageImpl::OnSetActive](../Topic/CSnapInPropertyPageImpl::OnSetActive.md)|Вызываемый платформой, если текущая страница становится активным.|  
|[CSnapInPropertyPageImpl::OnWizardBack](../Topic/CSnapInPropertyPageImpl::OnWizardBack.md)|Вызываемый платформой, когда пользователь нажимает кнопку **Back** при использовании страницу свойств мастер\- типа.|  
|[CSnapInPropertyPageImpl::OnWizardFinish](../Topic/CSnapInPropertyPageImpl::OnWizardFinish.md)|Вызываемый платформой, когда пользователь нажимает кнопку **Готово** при использовании страницу свойств мастер\- типа.|  
|[CSnapInPropertyPageImpl::OnWizardNext](../Topic/CSnapInPropertyPageImpl::OnWizardNext.md)|Вызываемый платформой, когда пользователь нажимает кнопку `Next` при использовании страницу свойств мастер\- типа.|  
|[CSnapInPropertyPageImpl::QuerySiblings](../Topic/CSnapInPropertyPageImpl::QuerySiblings.md)|Переадресует текущее сообщение ко всем страницам страницы свойств.|  
|[CSnapInPropertyPageImpl::SetModified](../Topic/CSnapInPropertyPageImpl::SetModified.md)|Вызов, чтобы активировать или отключить кнопку **Применить**.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CSnapInPropertyPageImpl::m\_psp](../Topic/CSnapInPropertyPageImpl::m_psp.md)|Структура Windows **PROPSHEETPAGE**, используемая объектом `CSnapInPropertyPageImpl`.|  
  
## Заметки  
 `CSnapInPropertyPageImpl` предоставляет базовую реализацию для объекта страницы свойств оснастки.  Основные функции страницы свойств реализуются с помощью оснастки несколько различных интерфейсов и сопоставить типы.  
  
## Иерархия наследования  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## Требования  
 **Header:**  atlsnap.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)