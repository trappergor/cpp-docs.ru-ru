---
title: "CAtlExeModuleT Class | Microsoft Docs"
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
  - "ATL::CAtlExeModuleT<T>"
  - "CAtlExeModuleT"
  - "ATL.CAtlExeModuleT<T>"
  - "ATL::CAtlExeModuleT"
  - "ATL.CAtlExeModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlExeModuleT class"
ms.assetid: 82245f3d-91d4-44fa-aa86-7cc7fbd758d9
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlExeModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет модуль для приложения.  
  
## Синтаксис  
  
```  
  
      template <  
   class T   
>  
class ATL_NO_VTABLE CAtlExeModuleT :  
   public CAtlModuleT< T >  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `CAtlExeModuleT`.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlExeModuleT::CAtlExeModuleT](../Topic/CAtlExeModuleT::CAtlExeModuleT.md)|Конструктор.|  
|[CAtlExeModuleT::~CAtlExeModuleT](../Topic/CAtlExeModuleT::~CAtlExeModuleT.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlExeModuleT::InitializeCom](../Topic/CAtlExeModuleT::InitializeCom.md)|Инициализирует модель COM.|  
|[CAtlExeModuleT::ParseCommandLine](../Topic/CAtlExeModuleT::ParseCommandLine.md)|Выполняет синтаксический анализ командной строки и выполняет регистрацию если требуемый.|  
|[CAtlExeModuleT::PostMessageLoop](../Topic/CAtlExeModuleT::PostMessageLoop.md)|Этот метод вызывается сразу после цикл сообщений ".|  
|[CAtlExeModuleT::PreMessageLoop](../Topic/CAtlExeModuleT::PreMessageLoop.md)|Этот метод вызывается сразу после того, как вставка цикла обработки сообщений.|  
|[CAtlExeModuleT::RegisterClassObjects](../Topic/CAtlExeModuleT::RegisterClassObjects.md)|Регистрирует объект класса.|  
|[CAtlExeModuleT::RevokeClassObjects](../Topic/CAtlExeModuleT::RevokeClassObjects.md)|Отменяет объекта класса.|  
|[CAtlExeModuleT::Run](../Topic/CAtlExeModuleT::Run.md)|Этот метод выполняет код в модуль EXE для инициализации, выполняет цикл обработки сообщений и очищает.|  
|[CAtlExeModuleT::RunMessageLoop](../Topic/CAtlExeModuleT::RunMessageLoop.md)|Этот метод выполняет цикл обработки сообщений.|  
|[CAtlExeModuleT::UninitializeCom](../Topic/CAtlExeModuleT::UninitializeCom.md)|Модель COM Uninitializes.|  
|[CAtlExeModuleT::Unlock](../Topic/CAtlExeModuleT::Unlock.md)|Уменьшает объем блокирования модуля.|  
|[CAtlExeModuleT::WinMain](../Topic/CAtlExeModuleT::WinMain.md)|Этот метод реализует код, необходимый для запуска исполняемого файла.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlExeModuleT::m\_bDelayShutdown](../Topic/CAtlExeModuleT::m_bDelayShutdown.md)|Пометить что указывает на то, что должно быть задержка выключая модуль.|  
|[CAtlExeModuleT::m\_dwPause](../Topic/CAtlExeModuleT::m_dwPause.md)|Значение паузы, используемый для предоставления все объекты освобождено перед выполнением действия.|  
|[CAtlExeModuleT::m\_dwTimeOut](../Topic/CAtlExeModuleT::m_dwTimeOut.md)|Значение времени ожидания, чтобы отложить выгрузка модуля.|  
  
## Заметки  
 `CAtlExeModuleT` представляет модуль приложения \(EXE\) и содержит код, который поддерживает создание EXE, обработке командной строке при регистрации класс возражает, выполнение цикла обработки сообщений и очистка на оставить.  
  
 Этот класс предназначен для повышения производительности, когда COM\-объект на сервере EXE окончательно созданы и уничтожаются.  После того как последнее com\-объекты освобождено, EXE ожидает длительность указанную элементом данных [CAtlExeModuleT::m\_dwTimeOut](../Topic/CAtlExeModuleT::m_dwTimeOut.md).  Если пользователь не выполняет никаких действий в данный момент \(т е отсутствие com\-объекты не созданы\), то процесс завершения работы проведен.  
  
 Элемент данных [CAtlExeModuleT::m\_bDelayShutdown](../Topic/CAtlExeModuleT::m_bDelayShutdown.md) пометить, используемый для определения, является ли EXE должно использует механизм, определенный выше.  Если он имеет значение false, то модуль завершается немедленно.  
  
 Дополнительные сведения о модулях в библиотеке ATL см. в разделе [Классы модуля библиотеки ATL](../Topic/ATL%20Module%20Classes.md).  
  
## Иерархия наследования  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CAtlExeModuleT`  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [Образец ATLDuck](../../top/visual-cpp-samples.md)   
 [CAtlModuleT Class](../../atl/reference/catlmodulet-class.md)   
 [CAtlDllModuleT Class](../../atl/reference/catldllmodulet-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)