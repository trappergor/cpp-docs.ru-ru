---
title: "CSnapInItemImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSnapInItemImpl"
  - "ATL.CSnapInItemImpl"
  - "ATL::CSnapInItemImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSnapInItemImpl class"
  - "snap-ins"
  - "snap-ins, ATL support for"
  - "snap-ins, data items"
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSnapInItemImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для реализации объект узла оснастки.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template <  
class T,  
BOOL bIsExtension= FALSE  
>  
class ATL_NO_VTABLE CSnapInItemImpl :  
public CSnapInItem  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `CSnapInItemImpl`.  
  
 *bIsExtension*  
 **TRUE** если объект расширения оснастки; в противном случае **FALSE**.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSnapInItemImpl::CSnapInItemImpl](../Topic/CSnapInItemImpl::CSnapInItemImpl.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSnapInItemImpl::AddMenuItems](../Topic/CSnapInItemImpl::AddMenuItems.md)|Добавляет пункты меню в контекстное меню.|  
|[CSnapInItemImpl::Command](../Topic/CSnapInItemImpl::Command.md)|Консолью, вызываемый, когда пользовательский будет выбрать пункт меню.|  
|[CSnapInItemImpl::CreatePropertyPages](../Topic/CSnapInItemImpl::CreatePropertyPages.md)|Добавляет страницы к странице свойств оснастки.|  
|[CSnapInItemImpl::FillData](../Topic/CSnapInItemImpl::FillData.md)|Данные копий в объекте оснастки в указанный поток.|  
|[CSnapInItemImpl::GetResultPaneInfo](../Topic/CSnapInItemImpl::GetResultPaneInfo.md)|Извлекает структуру **RESULTDATAITEM** оснастки.|  
|[CSnapInItemImpl::GetResultViewType](../Topic/CSnapInItemImpl::GetResultViewType.md)|Указывает тип представления, используемый областью результатов.|  
|[CSnapInItemImpl::GetScopePaneInfo](../Topic/CSnapInItemImpl::GetScopePaneInfo.md)|Извлекает структуру **SCOPEDATAITEM** оснастки.|  
|[CSnapInItemImpl::Notify](../Topic/CSnapInItemImpl::Notify.md)|Консолью, вызываемый для уведомления оснастка действий, выполненных пользователем.|  
|[CSnapInItemImpl::QueryPagesFor](../Topic/CSnapInItemImpl::QueryPagesFor.md)|Вызываемый для просмотра, если узел поддерживает оснастки страницы свойств.|  
|[CSnapInItemImpl::SetMenuInsertionFlags](../Topic/CSnapInItemImpl::SetMenuInsertionFlags.md)|Изменяет флаги меню для вставки объекта оснастки.|  
|[CSnapInItemImpl::SetToolbarButtonInfo](../Topic/CSnapInItemImpl::SetToolbarButtonInfo.md)|Задает параметры указанной кнопки панели инструментов.|  
|[CSnapInItemImpl::UpdateMenuState](../Topic/CSnapInItemImpl::UpdateMenuState.md)|Обновляет состояние элемента контекстного меню.|  
|[CSnapInItemImpl::UpdateToolbarButton](../Topic/CSnapInItemImpl::UpdateToolbarButton.md)|Обновляет состояние указанной кнопки панели инструментов.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CSnapInItemImpl::m\_bstrDisplayName](../Topic/CSnapInItemImpl::m_bstrDisplayName.md)|Имя объекта оснастки.|  
|[CSnapInItemImpl::m\_resultDataItem](../Topic/CSnapInItemImpl::m_resultDataItem.md)|Структура Windows **RESULTDATAITEM**, используемая объектом `CSnapInItemImpl`.|  
|[CSnapInItemImpl::m\_scopeDataItem](../Topic/CSnapInItemImpl::m_scopeDataItem.md)|Структура Windows **SCOPEDATAITEM**, используемая объектом `CSnapInItemImpl`.|  
  
## Заметки  
 `CSnapInItemImpl` предоставляет базовую реализацию для объекта узла оснастки, например добавление пунктов меню и панелей инструментов, а переадресующ команды для узла оснастки к соответствующему обработчику функция.  Эти функции реализуются с помощью нескольких различных интерфейсов и сопоставить типы.  Уведомления маркеров реализации значения по умолчанию, отправляемые в узел объект, указав правильный экземпляр производного класса, а затем переадресованы сообщения с правильным экземпляром.  
  
## Иерархия наследования  
 `CSnapInItem`  
  
 `CSnapInItemImpl`  
  
## Требования  
 **Header:**  atlsnap.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)