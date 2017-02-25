---
title: "COleControlSite Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControlSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControlSite class"
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleControlSite Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Обеспечивает поддержку пользовательских клиентских интерфейсов элемента управления.  
  
## Синтаксис  
  
```  
class COleControlSite : public CCmdTarget  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleControlSite::COleControlSite](../Topic/COleControlSite::COleControlSite.md)|Создает объект `COleControlSite`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleControlSite::BindDefaultProperty](../Topic/COleControlSite::BindDefaultProperty.md)|Привязывает свойство по умолчанию размещенного элемента управления к источнику данных.|  
|[COleControlSite::BindProperty](../Topic/COleControlSite::BindProperty.md)|Привязывает свойство размещенного элемента управления к источнику данных.|  
|[COleControlSite::CreateControl](../Topic/COleControlSite::CreateControl.md)|Создает размещенный элемент управления ActiveX.|  
|[COleControlSite::DestroyControl](../Topic/COleControlSite::DestroyControl.md)|Удаляет элемент управления ведущего приложения.|  
|[COleControlSite::DoVerb](../Topic/COleControlSite::DoVerb.md)|Выполняет указанную команду размещаемого элемента управления.|  
|[COleControlSite::EnableDSC](../Topic/COleControlSite::EnableDSC.md)|Включает получение данных для сайта элемента управления.|  
|[COleControlSite::EnableWindow](../Topic/COleControlSite::EnableWindow.md)|Включает сайт элемента управления.|  
|[COleControlSite::FreezeEvents](../Topic/COleControlSite::FreezeEvents.md)|Определяет, если сайт элемента управления принимает события.|  
|[COleControlSite::GetDefBtnCode](../Topic/COleControlSite::GetDefBtnCode.md)|Извлекает код кнопку по умолчанию для размещаемого элемента управления.|  
|[COleControlSite::GetDlgCtrlID](../Topic/COleControlSite::GetDlgCtrlID.md)|Извлекает идентификатор элемента управления.|  
|[COleControlSite::GetEventIID](../Topic/COleControlSite::GetEventIID.md)|Извлекает идентификатор интерфейса события для размещаемого элемента управления.|  
|[COleControlSite::GetExStyle](../Topic/COleControlSite::GetExStyle.md)|Получает расширенные стили сайта элемента управления.|  
|[COleControlSite::GetProperty](../Topic/COleControlSite::GetProperty.md)|Извлекает указанное свойство размещаемого элемента управления.|  
|[COleControlSite::GetStyle](../Topic/COleControlSite::GetStyle.md)|Получает стили сайта элемента управления.|  
|[COleControlSite::GetWindowText](../Topic/COleControlSite::GetWindowText.md)|Извлекает текст размещаемого элемента управления.|  
|[COleControlSite::InvokeHelper](../Topic/COleControlSite::InvokeHelper.md)|Вызывает определенный метод размещаемого элемента управления.|  
|[COleControlSite::InvokeHelperV](../Topic/COleControlSite::InvokeHelperV.md)|Вызывает определенный метод размещенного элемента управления с переменным списком аргументов.|  
|[COleControlSite::IsDefaultButton](../Topic/COleControlSite::IsDefaultButton.md)|Определяет, является ли элемент управления кнопку по умолчанию в окне.|  
|[COleControlSite::IsWindowEnabled](../Topic/COleControlSite::IsWindowEnabled.md)|Проверяет отображается состояние сайта элемента управления.|  
|[COleControlSite::ModifyStyle](../Topic/COleControlSite::ModifyStyle.md)|Изменяет существующие расширенные стили сайта элемента управления.|  
|[COleControlSite::ModifyStyleEx](../Topic/COleControlSite::ModifyStyleEx.md)|Изменяет текущее стили сайта элемента управления.|  
|[COleControlSite::MoveWindow](../Topic/COleControlSite::MoveWindow.md)|Изменяет положение сайта элемента управления.|  
|[COleControlSite::QuickActivate](../Topic/COleControlSite::QuickActivate.md)|Быстрые активировать размещенные размещенный элемент управления.|  
|[COleControlSite::SafeSetProperty](../Topic/COleControlSite::SafeSetProperty.md)|Задает свойство или метод элемента управления без вероятность возникновения исключения.|  
|[COleControlSite::SetDefaultButton](../Topic/COleControlSite::SetDefaultButton.md)|Задает кнопку по умолчанию в окне.|  
|[COleControlSite::SetDlgCtrlID](../Topic/COleControlSite::SetDlgCtrlID.md)|Извлекает идентификатор элемента управления.|  
|[COleControlSite::SetFocus](../Topic/COleControlSite::SetFocus.md)|Устанавливает фокус к сайту элемента управления.|  
|[COleControlSite::SetProperty](../Topic/COleControlSite::SetProperty.md)|Устанавливает конкретное свойство размещаемого элемента управления.|  
|[COleControlSite::SetPropertyV](../Topic/COleControlSite::SetPropertyV.md)|Устанавливает конкретное свойство размещенного элемента управления с переменным списком аргументов.|  
|[COleControlSite::SetWindowPos](../Topic/COleControlSite::SetWindowPos.md)|Задает положение сайта элемента управления.|  
|[COleControlSite::SetWindowText](../Topic/COleControlSite::SetWindowText.md)|Устанавливает текст размещаемого элемента управления.|  
|[COleControlSite::ShowWindow](../Topic/COleControlSite::ShowWindow.md)|Показать или скрывает сайт элемента управления.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleControlSite::GetControlInfo](../Topic/COleControlSite::GetControlInfo.md)|Извлекает данные и назначенные клавиши клавиатуры для размещаемого элемента управления.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COleControlSite::m\_bIsWindowless](../Topic/COleControlSite::m_bIsWindowless.md)|Определяет, находится ли размещенный элемент управления безоконный элемент управления.|  
|[COleControlSite::m\_ctlInfo](../Topic/COleControlSite::m_ctlInfo.md)|Содержит сведения об обработке клавиатуры для элемента управления.|  
|[COleControlSite::m\_dwEventSink](../Topic/COleControlSite::m_dwEventSink.md)|Файл cookie точки подключения элемента управления.|  
|[COleControlSite::m\_dwMiscStatus](../Topic/COleControlSite::m_dwMiscStatus.md)|Различные состояния для размещаемого элемента управления.|  
|[COleControlSite::m\_dwPropNotifySink](../Topic/COleControlSite::m_dwPropNotifySink.md)|Файл cookie `IPropertyNotifySink` элемента управления.|  
|[COleControlSite::m\_dwStyle](../Topic/COleControlSite::m_dwStyle.md)|Стили размещаемого элемента управления.|  
|[COleControlSite::m\_hWnd](../Topic/COleControlSite::m_hWnd.md)|Дескриптор сайта элемента управления.|  
|[COleControlSite::m\_iidEvents](../Topic/COleControlSite::m_iidEvents.md)|Идентификатор интерфейса события для размещаемого элемента управления.|  
|[COleControlSite::m\_nID](../Topic/COleControlSite::m_nID.md)|Идентификатор размещенного элемента управления.|  
|[COleControlSite::m\_pActiveObject](../Topic/COleControlSite::m_pActiveObject.md)|Указатель на объект `IOleInPlaceActiveObject` размещаемого элемента управления.|  
|[COleControlSite::m\_pCtrlCont](../Topic/COleControlSite::m_pCtrlCont.md)|Контейнер размещаемого элемента управления.|  
|[COleControlSite::m\_pInPlaceObject](../Topic/COleControlSite::m_pInPlaceObject.md)|Указатель на объект `IOleInPlaceObject` размещаемого элемента управления.|  
|[COleControlSite::m\_pObject](../Topic/COleControlSite::m_pObject.md)|Указатель на интерфейс `IOleObjectInterface` элемента управления.|  
|[COleControlSite::m\_pWindowlessObject](../Topic/COleControlSite::m_pWindowlessObject.md)|Указатель на интерфейс `IOleInPlaceObjectWindowless` элемента управления.|  
|[COleControlSite::m\_pWndCtrl](../Topic/COleControlSite::m_pWndCtrl.md)|Указатель на объект окна для размещаемого элемента управления.|  
|[COleControlSite::m\_rect](../Topic/COleControlSite::m_rect.md)|Измерения сайта элемента управления.|  
  
## Заметки  
 Эта поддержка первичные середины, внедренный элемент управления ActiveX возвращает сведения о расположении и экстенты его сайта отображения своего моникера, своего пользовательского интерфейса, его свойства окружения и других ресурсов, предоставляемых его контейнером.  `COleControlSite` полностью реализует [IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502), [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706), [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), **IBoundObjectSite**, **INotifyDBEvents**, интерфейсы [IRowSetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx).  Кроме того, интерфейс IDispatch \(предоставляет поддержку свойства окружения и приемников событий\) также реализован.  
  
 Чтобы создать сайт элемента управления ActiveX с помощью `COleControlSite`, наследуйте класс от `COleControlSite`.  В `CWnd`\- производном классе для диалогового окна\) переопределения сегмента \(например, функция **CWnd::CreateControlSite**.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `COleControlSite`  
  
## Требования  
 **Header:** afxocc.h  
  
## См. также  
 [CCmdTarget Class](../Topic/CCmdTarget%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleControlContainer Class](../../mfc/reference/colecontrolcontainer-class.md)