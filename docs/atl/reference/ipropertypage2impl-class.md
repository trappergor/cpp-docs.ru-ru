---
title: "IPropertyPage2Impl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPropertyPage2Impl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage2 ATL implementation"
  - "IPropertyPage2Impl class"
  - "страницы свойств"
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IPropertyPage2Impl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует **IUnknown** и наследует реализацию по умолчанию [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template< class   
      T  
      >  
class IPropertyPage2Impl : public IPropertyPageImpl< T>  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IPropertyPage2Impl`.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IPropertyPage2Impl::EditProperty](../Topic/IPropertyPage2Impl::EditProperty.md)|Определяет свойства, элемент управления получает фокус, когда страница свойств будет активируется.  Реализация библиотеки ATL возвращает **E\_NOTIMPL**.|  
  
## Заметки  
 Интерфейс [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) расширяет [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) путем добавления метода `EditProperty`.  Этот метод позволяет клиенту выбрать конкретное свойство в объекте страницы свойств.  
  
 Класс `IPropertyPage2Impl` просто возвращает **E\_NOTIMPL** для **IPropertyPage2::EditProperty**.  Однако он наследует реализацию по умолчанию [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) и реализует **IUnknown**, отправляя данные на устройство резервного копирования в отладочные построения.  
  
 При создании страницы свойств класс обычно является производным от `IPropertyPageImpl`.  Чтобы обеспечить дополнительную поддержку **IPropertyPage2** измените определение класса, и переопределить метод `EditProperty`.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [IPerPropertyBrowsingImpl Class](../Topic/IPerPropertyBrowsingImpl%20Class.md)   
 [ISpecifyPropertyPagesImpl Class](../Topic/ISpecifyPropertyPagesImpl%20Class.md)   
 [Class Overview](../../atl/atl-class-overview.md)