---
title: "CMFCDropDownToolbarButton Class | Microsoft Docs"
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
  - "CMFCDropDownToolbarButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCDropDownToolbarButton class"
  - "OnCancelMode method"
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
caps.latest.revision: 31
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDropDownToolbarButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Тип кнопки панели инструментов ведет себя как обычная кнопку при ее нажата.  Однако он открывает панель инструментов падающую вниз \([CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md) если нажатия и удерживания пользователем кнопки панели инструментов.  
  
## Синтаксис  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](../Topic/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton.md)|Создает объект `CMFCDropDownToolbarButton`.|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCDropDownToolbarButton::CopyFrom](../Topic/CMFCDropDownToolbarButton::CopyFrom.md)|Копирует свойства другой кнопки панели инструментов с текущим кнопке.  \(Переопределяет [CMFCToolBarButton::CopyFrom](../Topic/CMFCToolBarButton::CopyFrom.md)\).|  
|`CMFCDropDownToolbarButton::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|[CMFCDropDownToolbarButton::DropDownToolbar](../Topic/CMFCDropDownToolbarButton::DropDownToolbar.md)|Открывает панель инструментов падающую вниз.|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](../Topic/CMFCDropDownToolbarButton::ExportToMenuButton.md)|Копии вставке СМС из кнопок панели инструментов в меню.  \(Переопределяет [CMFCToolBarButton::ExportToMenuButton](../Topic/CMFCToolBarButton::ExportToMenuButton.md)\).|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](../Topic/CMFCDropDownToolbarButton::GetDropDownToolBar.md)|Извлекает раскрывающаяся панель инструментов, которая сопоставлена с кнопкой.|  
|`CMFCDropDownToolbarButton::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
|[CMFCDropDownToolbarButton::IsDropDown](../Topic/CMFCDropDownToolbarButton::IsDropDown.md)|Определяет, является ли панель инструментов в данный момент раскрывающаяся открыта.|  
|[CMFCDropDownToolbarButton::IsExtraSize](../Topic/CMFCDropDownToolbarButton::IsExtraSize.md)|Определяет, является ли кнопка может отображаться с расширенной границей.  \(Переопределяет [CMFCToolBarButton::IsExtraSize](../Topic/CMFCToolBarButton::IsExtraSize.md)\).|  
|[CMFCDropDownToolbarButton::OnCalculateSize](../Topic/CMFCDropDownToolbarButton::OnCalculateSize.md)|Вызываемый платформой, чтобы вычислить размер кнопки для указанного контекста устройства и состояния закрепления.  \(Переопределяет [CMFCToolBarButton::OnCalculateSize](../Topic/CMFCToolBarButton::OnCalculateSize.md)\).|  
|`CMFCDropDownToolbarButton::OnCancelMode`|Вызываемый платформой для обработки сообщения [WM\_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615).  \(Переопределяет `CMCToolBarButton::OnCancelMode`\).|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](../Topic/CMFCDropDownToolbarButton::OnChangeParentWnd.md)|Вызываемый платформой, если кнопка будет вставлена в новую панель инструментов.  \(Переопределяет [CMFCToolBarButton::OnChangeParentWnd](../Topic/CMFCToolBarButton::OnChangeParentWnd.md)\).|  
|[CMFCDropDownToolbarButton::OnClick](../Topic/CMFCDropDownToolbarButton::OnClick.md)|Вызываемый платформой, когда пользователь нажимает кнопку мыши.  \(Переопределяет [CMFCToolBarButton::OnClick](../Topic/CMFCToolBarButton::OnClick.md)\).|  
|[CMFCDropDownToolbarButton::OnClickUp](../Topic/CMFCDropDownToolbarButton::OnClickUp.md)|Вызываемый платформой, когда пользователь освобождает кнопки мыши.  \(Переопределяет [CMFCToolBarButton::OnClickUp](../Topic/CMFCToolBarButton::OnClickUp.md)\).|  
|[CMFCDropDownToolbarButton::OnContextHelp](../Topic/CMFCDropDownToolbarButton::OnContextHelp.md)|Вызываемый платформой если панель инструментов `WM_HELPHITTEST` родителя обрабатывающий сообщение.  \(Переопределяет [CMFCToolBarButton::OnContextHelp](../Topic/CMFCToolBarButton::OnContextHelp.md)\).|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](../Topic/CMFCDropDownToolbarButton::OnCustomizeMenu.md)|Изменяет предоставленный меню, когда приложение отображает контекстное меню в родительской панели инструментов.  \(Переопределяет [CMFCToolBarButton::OnCustomizeMenu](../Topic/CMFCToolBarButton::OnCustomizeMenu.md)\).|  
|[CMFCDropDownToolbarButton::OnDraw](../Topic/CMFCDropDownToolbarButton::OnDraw.md)|Вызываемый платформой для рисования кнопки с помощью указанных стилей и параметров.  \(Переопределяет [CMFCToolBarButton::OnDraw](../Topic/CMFCToolBarButton::OnDraw.md)\).|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](../Topic/CMFCDropDownToolbarButton::OnDrawOnCustomizeList.md)|Вызываемый платформой для рисования кнопки на панели **Команды** диалогового окна **Настроить**.  \(Переопределяет [CMFCToolBarButton::OnDrawOnCustomizeList](../Topic/CMFCToolBarButton::OnDrawOnCustomizeList.md)\).|  
|[CMFCDropDownToolbarButton::Serialize](../Topic/CMFCDropDownToolbarButton::Serialize.md)|Считывает этот объект из архива или записывает его в архив.  \(Переопределяет [CMFCToolBarButton::Serialize](../Topic/CMFCToolBarButton::Serialize.md)\).|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](../Topic/CMFCDropDownToolbarButton::SetDefaultCommand.md)|Задает команду, которую инфраструктура использует по умолчанию, когда пользователь нажимает кнопку.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCDropDownToolbarButton::m\_uiShowBarDelay](../Topic/CMFCDropDownToolbarButton::m_uiShowBarDelay.md)|Определяет продолжительность времени, что пользователь должен содержать кнопки мыши до раскрывающаяся панель инструментов отображается.|  
  
## Заметки  
 `CMFCDropDownToolBarButton` отличается от обычной кнопки, что он имеет небольшой низк\- стрелку в правом углу кнопки.  После того как пользователь выбирает из раскрывающейся кнопки панели инструментов, указывающие его границы значка на кнопке панели инструментов верхнего уровня \(кнопка с небольшой стрелкой в низк\- правом углу\).  
  
 Сведения о том, как реализовать панель инструментов падающую вниз см. в разделе [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md).  
  
 Объект `CMFCDropDownToolBarButton` можно экспортировать в объект [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md) и показать, как кнопка меню с всплывающим меню.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## Требования  
 **заголовок:**  afxdropdowntoolbar.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCDropDownToolBar Class](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarMenuButton Class](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [Пошаговое руководство. Размещение элементов управления на панели инструментов](../../mfc/walkthrough-putting-controls-on-toolbars.md)