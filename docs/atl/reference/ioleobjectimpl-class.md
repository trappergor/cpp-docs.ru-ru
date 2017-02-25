---
title: "IOleObjectImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IOleObjectImpl"
  - "ATL.IOleObjectImpl<T>"
  - "ATL::IOleObjectImpl"
  - "ATL::IOleObjectImpl<T>"
  - "IOleObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления ActiveX [C++], communication between container and control"
  - "IOleObject, ATL -реализация"
  - "IOleObjectImpl class"
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IOleObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует **IUnknown** и основной интерфейс, через который контейнер взаимодействует с элементом управления.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IOleObjectImpl :  
public IOleObject  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IOleObjectImpl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IOleObjectImpl::Advise](../Topic/IOleObjectImpl::Advise.md)|Устанавливает вспомогательное соединение с элементом управления.|  
|[IOleObjectImpl::Close](../Topic/IOleObjectImpl::Close.md)|Изменяет состояние элемента управления из скриптов в загруженный.|  
|[IOleObjectImpl::DoVerb](../Topic/IOleObjectImpl::DoVerb.md)|Указывает элемент управления для выполнения одной из перечисленных действий.|  
|[IOleObjectImpl::DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md)|Указывает, что элемент управления отменяет какое\-либо состояние отката он поддерживает.|  
|[IOleObjectImpl::DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md)|Указывает, что элемент управления удаляет его пользовательский интерфейс из представления.|  
|[IOleObjectImpl::DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md)|Запускает элемент управления и установит его окно, но не установит пользовательского интерфейса элемента управления.|  
|[IOleObjectImpl::DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md)|Вызывает элемент управления необходимо редактировать в отдельном окне.|  
|[IOleObjectImpl::DoVerbPrimary](../Topic/IOleObjectImpl::DoVerbPrimary.md)|Выполняет указанное действие, когда пользователь дважды щелкает элемент управления.  Элемент управления определяет действие, обычно активировать в\- размещение элемента управления.|  
|[IOleObjectImpl::DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md)|Указывает новому вставленному элементу управления для пользователя.|  
|[IOleObjectImpl::DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md)|Активировать в\- размещение элемента управления и отображает элемент пользовательского интерфейса элемента управления, например, меню и панели инструментов.|  
|[IOleObjectImpl::EnumAdvise](../Topic/IOleObjectImpl::EnumAdvise.md)|Перечисляет подключения элемента управления вспомогательных.|  
|[IOleObjectImpl::EnumVerbs](../Topic/IOleObjectImpl::EnumVerbs.md)|Перечисляет действия для элемента управления.|  
|[IOleObjectImpl::GetClientSite](../Topic/IOleObjectImpl::GetClientSite.md)|Извлекает сайт клиента элемента управления.|  
|[IOleObjectImpl::GetClipboardData](../Topic/IOleObjectImpl::GetClipboardData.md)|Извлекает данные из буфера обмена.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IOleObjectImpl::GetExtent](../Topic/IOleObjectImpl::GetExtent.md)|Получает экстент области отображения элемента управления.|  
|[IOleObjectImpl::GetMiscStatus](../Topic/IOleObjectImpl::GetMiscStatus.md)|Извлекает состояние элемента управления.|  
|[IOleObjectImpl::GetMoniker](../Topic/IOleObjectImpl::GetMoniker.md)|Возвращает моникер элемента управления.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IOleObjectImpl::GetUserClassID](../Topic/IOleObjectImpl::GetUserClassID.md)|Извлекает идентификатор класса элемента управления.|  
|[IOleObjectImpl::GetUserType](../Topic/IOleObjectImpl::GetUserType.md)|Извлекает имя пользовательского типа элемента управления.|  
|[IOleObjectImpl::InitFromData](../Topic/IOleObjectImpl::InitFromData.md)|Инициализирует элемент управления из выбранные данные.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IOleObjectImpl::IsUpToDate](../Topic/IOleObjectImpl::IsUpToDate.md)|Проверяет, является ли элемент управления актуален.  Реализация библиотеки ATL возвращает `S_OK`.|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](../Topic/IOleObjectImpl::OnPostVerbDiscardUndo.md)|Вызываемый после [DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md) состояния rollback отменяет.|  
|[IOleObjectImpl::OnPostVerbHide](../Topic/IOleObjectImpl::OnPostVerbHide.md)|Вызываемый [DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md) после элемента управления скрывается.|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](../Topic/IOleObjectImpl::OnPostVerbInPlaceActivate.md)|Вызываемый [DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md) после того как элемент управления будет активировать на месте.|  
|[IOleObjectImpl::OnPostVerbOpen](../Topic/IOleObjectImpl::OnPostVerbOpen.md)|Вызываемый [DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md) после того как элемент управления будет открыт для редактирования в отдельном окне.|  
|[IOleObjectImpl::OnPostVerbShow](../Topic/IOleObjectImpl::OnPostVerbShow.md)|Вызываемый [DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md) после того как элемент управления будет сделан видимым.|  
|[IOleObjectImpl::OnPostVerbUIActivate](../Topic/IOleObjectImpl::OnPostVerbUIActivate.md)|Вызываемый [DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md) после пользовательского интерфейса элемента управления будет активировать.|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](../Topic/IOleObjectImpl::OnPreVerbDiscardUndo.md)|Вызываемый [DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md) состоянием отката до отмены.|  
|[IOleObjectImpl::OnPreVerbHide](../Topic/IOleObjectImpl::OnPreVerbHide.md)|Вызываемый [DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md) перед элементом управления скрывается.|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](../Topic/IOleObjectImpl::OnPreVerbInPlaceActivate.md)|Вызываемый [DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md) до того, как элемент управления будет активировать на месте.|  
|[IOleObjectImpl::OnPreVerbOpen](../Topic/IOleObjectImpl::OnPreVerbOpen.md)|Вызываемый [DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md) до того, как элемент управления будет открыт для редактирования в отдельном окне.|  
|[IOleObjectImpl::OnPreVerbShow](../Topic/IOleObjectImpl::OnPreVerbShow.md)|Вызываемый [DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md) до того, как элемент управления будет сделан видимым.|  
|[IOleObjectImpl::OnPreVerbUIActivate](../Topic/IOleObjectImpl::OnPreVerbUIActivate.md)|Прежде чем [DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md) с именем пользовательского интерфейса элемента управления будет активировать.|  
|[IOleObjectImpl::SetClientSite](../Topic/IOleObjectImpl::SetClientSite.md)|Указывает элемент управления о своем сайте клиента в контейнере.|  
|[IOleObjectImpl::SetColorScheme](../Topic/IOleObjectImpl::SetColorScheme.md)|Рекомендуется цветовую схему к приложению элемента управления, если таковые имеются.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IOleObjectImpl::SetExtent](../Topic/IOleObjectImpl::SetExtent.md)|Задает область памяти области отображения элемента управления.|  
|[IOleObjectImpl::SetHostNames](../Topic/IOleObjectImpl::SetHostNames.md)|Указывает элемент управления имена контейнерного приложения и документа контейнера.|  
|[IOleObjectImpl::SetMoniker](../Topic/IOleObjectImpl::SetMoniker.md)|Указывает элемент управления, что его моникер.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
|[IOleObjectImpl::Unadvise](../Topic/IOleObjectImpl::Unadvise.md)|Удаляет вспомогательное соединение с элементом управления.|  
|[IOleObjectImpl::Update](../Topic/IOleObjectImpl::Update.md)|Обновляет элемент управления.  Реализация библиотеки ATL возвращает `S_OK`.|  
  
## Заметки  
 Интерфейс [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) основной интерфейс, через который контейнер взаимодействует с элементом управления.  Класс `IOleObjectImpl` предоставляет реализацию по умолчанию для интерфейса и реализуется **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IOleObject`  
  
 `IOleObjectImpl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Class Overview](../../atl/atl-class-overview.md)