---
title: "IPropertyPageImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPropertyPageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage ATL implementation"
  - "IPropertyPageImpl class"
  - "страницы свойств"
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPropertyPageImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует **IUnknown** и предоставляет реализацию по умолчанию для интерфейса [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template< class   
      T  
      >  
class IPropertyPageImpl  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IPropertyPageImpl`.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[IPropertyPageImpl::IPropertyPageImpl](../Topic/IPropertyPageImpl::IPropertyPageImpl.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IPropertyPageImpl::Activate](../Topic/IPropertyPageImpl::Activate.md)|Создает диалоговое окно страницы свойств.|  
|[IPropertyPageImpl::Apply](../Topic/IPropertyPageImpl::Apply.md)|Применяет текущие значения страницы свойств к основным объектам, определенным с помощью `SetObjects`.  Реализация библиотеки ATL возвращает `S_OK`.|  
|[IPropertyPageImpl::Deactivate](../Topic/IPropertyPageImpl::Deactivate.md)|Уничтожает окно, созданное с **Активировать**.|  
|[IPropertyPageImpl::GetPageInfo](../Topic/IPropertyPageImpl::GetPageInfo.md)|Извлекает сведения о странице свойств.|  
|[IPropertyPageImpl::Help](../Topic/IPropertyPageImpl::Help.md)|Вызывает справке Windows для страницы свойств.|  
|[IPropertyPageImpl::IsPageDirty](../Topic/IPropertyPageImpl::IsPageDirty.md)|Указывает изменялась ли страница свойств поскольку она была активируется.|  
|[IPropertyPageImpl::Move](../Topic/IPropertyPageImpl::Move.md)|Положения и размеры диалоговое окно страницы свойств.|  
|[IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md)|Пометит состояние страницы свойств, как изменен или без изменений.|  
|[IPropertyPageImpl::SetObjects](../Topic/IPropertyPageImpl::SetObjects.md)|Предоставляет массив указателей **IUnknown** для объектов, связанных со страницей свойств.  Эти объекты получают текущие значения страницы свойств через вызов **Применить**.|  
|[IPropertyPageImpl::SetPageSite](../Topic/IPropertyPageImpl::SetPageSite.md)|Предоставляет страницу свойств с указателем `IPropertyPageSite`, через который страница свойств взаимодействует с кадром свойства.|  
|[IPropertyPageImpl::Show](../Topic/IPropertyPageImpl::Show.md)|Открывает диалоговое окно страницы свойств видимой или невидимой.|  
|[IPropertyPageImpl::TranslateAccelerator](../Topic/IPropertyPageImpl::TranslateAccelerator.md)|Обрабатывает заданное нажатие клавиши.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[IPropertyPageImpl::m\_bDirty](../Topic/IPropertyPageImpl::m_bDirty.md)|Указывает, изменилось ли состояние страницы свойств.|  
|[IPropertyPageImpl::m\_dwDocString](../Topic/IPropertyPageImpl::m_dwDocString.md)|Хранит идентификатор ресурса, связанный с текстовая строка, описывающая страницу свойств.|  
|[IPropertyPageImpl::m\_dwHelpContext](../Topic/IPropertyPageImpl::m_dwHelpContext.md)|Хранит идентификатор контекста для раздела справки, связанную со страницей свойств.|  
|[IPropertyPageImpl::m\_dwHelpFile](../Topic/IPropertyPageImpl::m_dwHelpFile.md)|Хранит идентификатор ресурса, связанный с именем файла справки с описанием страницы свойств.|  
|[IPropertyPageImpl::m\_dwTitle](../Topic/IPropertyPageImpl::m_dwTitle.md)|Хранит идентификатор ресурса, связанный с текстовой строкой, которая появляется на вкладке страницы свойств.|  
|[IPropertyPageImpl::m\_nObjects](../Topic/IPropertyPageImpl::m_nObjects.md)|Хранит число объектов, связанных со страницей свойств.|  
|[IPropertyPageImpl::m\_pPageSite](../Topic/IPropertyPageImpl::m_pPageSite.md)|Указатель на интерфейс `IPropertyPageSite` через, страница свойств взаимодействует с кадром свойства.|  
|[IPropertyPageImpl::m\_ppUnk](../Topic/IPropertyPageImpl::m_ppUnk.md)|Указывает на массив указателей **IUnknown** в объекты, связанные с страницей свойств.|  
|[IPropertyPageImpl::m\_size](../Topic/IPropertyPageImpl::m_size.md)|Хранит высота и ширина диалогового окна страницы свойств в пикселях.|  
  
## Заметки  
 Интерфейс [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) предоставляет объект для управления указанная страница свойств на странице свойств.  Класс `IPropertyPageImpl` предоставляет реализацию по умолчанию для интерфейса и реализуется **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IPropertyPage`  
  
 `IPropertyPageImpl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [IPropertyPage2Impl Class](../../atl/reference/ipropertypage2impl-class.md)   
 [IPerPropertyBrowsingImpl Class](../Topic/IPerPropertyBrowsingImpl%20Class.md)   
 [ISpecifyPropertyPagesImpl Class](../Topic/ISpecifyPropertyPagesImpl%20Class.md)   
 [Class Overview](../../atl/atl-class-overview.md)