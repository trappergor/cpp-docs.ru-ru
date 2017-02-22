---
title: "CAtlAutoThreadModuleT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlAutoThreadModuleT"
  - "ATL::CAtlAutoThreadModuleT"
  - "CAtlAutoThreadModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlAutoThreadModuleT class"
ms.assetid: ae1667c6-3fb8-47bc-b35d-9ea5e9896d7f
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CAtlAutoThreadModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для реализации поток\- пул, сервер модели COM модели изоляции.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template <  
class T,  
class ThreadAllocator= CComSimpleThreadAllocator,  
DWORD dwWait= INFINITE   
>  
class ATL_NO_VTABLE CAtlAutoThreadModuleT :  
public IAtlAutoThreadModule  
```  
  
#### Параметры  
 `T`  
 Класс, который будет реализовывать сервер модели COM.  
  
 `ThreadAllocator`  
 Класс, выделение потока.  Значение по умолчанию [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md).  
  
 `dwWait`  
 Указывает интервал времени ожидания в миллисекундах.  По умолчанию используется значение INFINITE, что означает, что время ожидания метода никогда не истекает.  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlAutoThreadModuleT::GetDefaultThreads](../Topic/CAtlAutoThreadModuleT::GetDefaultThreads.md)|Эта статическая функция динамически вычисляет и возвращает максимальное количество потоков для модуля EXE\-ФАЙЛА на основе количества процессоров.|  
  
## Заметки  
 Класс [Класса CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) является производным от `CAtlAutoThreadModuleT` для реализации поток\- пул, сервер модели COM модели изоляции.  Оно заменяет класс [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) устарел.  
  
> [!NOTE]
>  Этот класс не должен использоваться в библиотеке DLL, по умолчанию используется значение `dwWait` ИНФИНИТНОГО вызовет взаимоблокировку, когда библиотека DLL будет.  
  
## Иерархия наследования  
 `IAtlAutoThreadModule`  
  
 `CAtlAutoThreadModuleT`  
  
## Требования  
 **Header:** atlbase.h  
  
## См. также  
 [IAtlAutoThreadModule Class](../../atl/reference/iatlautothreadmodule-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [IAtlAutoThreadModule Class](../../atl/reference/iatlautothreadmodule-class.md)   
 [Модульные классы](../Topic/ATL%20Module%20Classes.md)