---
title: "COleControlContainer Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControlContainer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "контейнер для элементов ActiveX [C++], control site"
  - "COleControlContainer class"
  - "пользовательские элементы управления [MFC], sites"
ms.assetid: f7ce9246-0fb7-4f07-a83a-6c2390d0fdf8
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleControlContainer Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Действует как контейнер элемента управления для элементов управления ActiveX.  
  
## Синтаксис  
  
```  
class COleControlContainer : public CCmdTarget  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleControlContainer::COleControlContainer](../Topic/COleControlContainer::COleControlContainer.md)|Создает объект `COleControlContainer`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleControlContainer::AttachControlSite](../Topic/COleControlContainer::AttachControlSite.md)|Создает сайт элемента управления является контейнером.|  
|[COleControlContainer::BroadcastAmbientPropertyChange](../Topic/COleControlContainer::BroadcastAmbientPropertyChange.md)|Сообщает все размещенного элемента управления, что внешнее свойство было изменено.|  
|[COleControlContainer::CheckDlgButton](../Topic/COleControlContainer::CheckDlgButton.md)|Изменяет заданный элемент управления "Кнопка".|  
|[COleControlContainer::CheckRadioButton](../Topic/COleControlContainer::CheckRadioButton.md)|Выбирает заданный переключатель группы.|  
|[COleControlContainer::CreateControl](../Topic/COleControlContainer::CreateControl.md)|Создает размещенный элемент управления ActiveX.|  
|[COleControlContainer::CreateOleFont](../Topic/COleControlContainer::CreateOleFont.md)|Создает OLE\-шрифт.|  
|[COleControlContainer::FindItem](../Topic/COleControlContainer::FindItem.md)|Возвращает пользовательский сайт управления.|  
|[COleControlContainer::FreezeAllEvents](../Topic/COleControlContainer::FreezeAllEvents.md)|Определяет, если сайт элемента управления принимает события.|  
|[COleControlContainer::GetAmbientProp](../Topic/COleControlContainer::GetAmbientProp.md)|Извлекает определенное внешнее свойство.|  
|[COleControlContainer::GetDlgItem](../Topic/COleControlContainer::GetDlgItem.md)|Извлекает указанный элемент управления диалогового окна.|  
|[COleControlContainer::GetDlgItemInt](../Topic/COleControlContainer::GetDlgItemInt.md)|Получает значение заданного элемента управления диалогового окна.|  
|[COleControlContainer::GetDlgItemText](../Topic/COleControlContainer::GetDlgItemText.md)|Возвращает заголовок указанного элемента управления диалогового окна.|  
|[COleControlContainer::HandleSetFocus](../Topic/COleControlContainer::HandleSetFocus.md)|Определяет, если контейнер обрабатывает сообщения `WM_SETFOCUS`.|  
|[COleControlContainer::HandleWindowlessMessage](../Topic/COleControlContainer::HandleWindowlessMessage.md)|Обрабатывает сообщения, отправляемые безоконному элементу управления.|  
|[COleControlContainer::IsDlgButtonChecked](../Topic/COleControlContainer::IsDlgButtonChecked.md)|Указывает состояние указанной кнопки.|  
|[COleControlContainer::OnPaint](../Topic/COleControlContainer::OnPaint.md)|Вызываемый для обновления является частью контейнера.|  
|[COleControlContainer::OnUIActivate](../Topic/COleControlContainer::OnUIActivate.md)|Вызываемый, когда элемент управления будет активированным в\- размещение.|  
|[COleControlContainer::OnUIDeactivate](../Topic/COleControlContainer::OnUIDeactivate.md)|Вызываемый, когда элемент управления будет выключенным.|  
|[COleControlContainer::ScrollChildren](../Topic/COleControlContainer::ScrollChildren.md)|Вызываемый платформой, когда сообщения прокрутки будут получены из дочернего окна.|  
|[COleControlContainer::SendDlgItemMessage](../Topic/COleControlContainer::SendDlgItemMessage.md)|Отправляет сообщение в элемент управления.|  
|[COleControlContainer::SetDlgItemInt](../Topic/COleControlContainer::SetDlgItemInt.md)|Устанавливает значение элемента управления.|  
|[COleControlContainer::SetDlgItemText](../Topic/COleControlContainer::SetDlgItemText.md)|Задает текст элемента управления.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COleControlContainer::m\_crBack](../Topic/COleControlContainer::m_crBack.md)|Цвет фона для контейнера.|  
|[COleControlContainer::m\_crFore](../Topic/COleControlContainer::m_crFore.md)|Цвет контейнера.|  
|[COleControlContainer::m\_listSitesOrWnds](../Topic/COleControlContainer::m_listSitesOrWnds.md)|Список поддерживаемых сайтов элемента управления.|  
|[COleControlContainer::m\_nWindowlessControls](../Topic/COleControlContainer::m_nWindowlessControls.md)|Число элементов управления размещенной безоконных.|  
|[COleControlContainer::m\_pOleFont](../Topic/COleControlContainer::m_pOleFont.md)|Указатель на OLE шрифтом сайта пользовательского элемента управления.|  
|[COleControlContainer::m\_pSiteCapture](../Topic/COleControlContainer::m_pSiteCapture.md)|Указатель к сайту элемента управления для захвата.|  
|[COleControlContainer::m\_pSiteFocus](../Topic/COleControlContainer::m_pSiteFocus.md)|Указатель на элемент управления, который в данный момент имеет фокус ввода.|  
|[COleControlContainer::m\_pSiteUIActive](../Topic/COleControlContainer::m_pSiteUIActive.md)|Указатель на элемент управления, который в данный момент активированное в\- размещение.|  
|[COleControlContainer::m\_pWnd](../Topic/COleControlContainer::m_pWnd.md)|Указатель на окно, реализующий контейнер элемента управления.|  
|[COleControlContainer::m\_siteMap](../Topic/COleControlContainer::m_siteMap.md)|Карты сайта.|  
  
## Заметки  
 Это делается путем предоставления поддержки для одного или нескольких сайтов \(элемент управления ActiveX, `COleControlSite`\).  `COleControlContainer` полностью реализует интерфейсы [IOleInPlaceFrame](http://msdn.microsoft.com/library/windows/desktop/ms692770) и [IOleContainer](http://msdn.microsoft.com/library/windows/desktop/ms690103), позволяя, содержащиеся элементы управления ActiveX для выполнения их квалификации как элементы в\- размещения.  
  
 Обычно этот класс используется в сочетании с `COccManager` и `COleControlSite` для реализации пользовательского контейнера элемента управления ActiveX с пользовательскими сайтами для одного или нескольких элементов управления ActiveX.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `COleControlContainer`  
  
## Требования  
 **Header:** afxocc.h  
  
## См. также  
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleControlSite Class](../../mfc/reference/colecontrolsite-class.md)   
 [COccManager Class](../../mfc/reference/coccmanager-class.md)