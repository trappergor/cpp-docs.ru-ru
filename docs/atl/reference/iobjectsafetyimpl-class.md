---
title: "IObjectSafetyImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IObjectSafetyImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "элементы управления [ATL], safe"
  - "IObjectSafety, ATL -реализация"
  - "IObjectSafetyImpl class"
  - "safe for scripting and initialization (controls)"
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IObjectSafetyImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет реализацию по умолчанию для интерфейса `IObjectSafety` чтобы предоставить клиент для извлечения и задать уровни безопасности объекта.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Синтаксис  
  
```  
  
      template <class   
      T  
      , DWORD   
      dwSupportedSafety  
      >  
class IObjectSafetyImpl  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `IObjectSafetyImpl`.  
  
 *dwSupportedSafety*  
 Определяет поддерживаемые параметры безопасности для элемента управления.  Может иметь одно из следующих значений:  
  
-   **INTERFACESAFE\_FOR\_UNTRUSTED\_CALLER** Интерфейс, заданный параметром `riid`[SetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::SetInterfaceSafetyOptions.md) должно быть выполнено безопасным для работы со скриптами.  
  
-   **INTERFACESAFE\_FOR\_UNTRUSTED\_DATA** Интерфейс, заданный параметром `riid``SetInterfaceSafetyOptions` должно быть выполнено безопасным для ненадежных данных во время инициализации.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::GetInterfaceSafetyOptions.md)|Возвращает параметры безопасности, поддерживаемые объектом, а также параметры безопасности в данный момент установлены для объекта.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::SetInterfaceSafetyOptions.md)|Делает safe объекта для инициализации или сценариев.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[IObjectSafetyImpl::m\_dwCurrentSafety](../Topic/IObjectSafetyImpl::m_dwCurrentSafety.md)|Сохраняет текущий уровень безопасности объекта.|  
  
## Заметки  
 Класс `IObjectSafetyImpl` предоставляет реализацию по умолчанию `IObjectSafety`.  Интерфейс `IObjectSafety` позволяет клиенту получить и задать уровни безопасности объекта.  Например, браузер через интернет может вызвать **IObjectSafety::SetInterfaceSafetyOptions** чтобы сделать safe элемента управления для инициализации или safe скриптов.  
  
 Обратите внимание, что [IMPLEMENTED\_CATEGORY](../Topic/IMPLEMENTED_CATEGORY.md) с помощью макроса **CATID\_SafeForScripting** и категориями **CATID\_SafeForInitializing** компонентными предоставляет альтернативный способ указания, что компонент является безопасным.  
  
 **Связанные статьи** [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md), [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Иерархия наследования  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [IObjectSafety Interface](https://msdn.microsoft.com/en-us/library/aa768224.aspx)   
 [Class Overview](../../atl/atl-class-overview.md)