---
title: "CDebugReportHook Class | Microsoft Docs"
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
  - "ATL.CDebugReportHook"
  - "CDebugReportHook"
  - "ATL::CDebugReportHook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDebugReportHook class"
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDebugReportHook Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс используется отправлять отладочные отчеты к именованному каналу.  
  
## Синтаксис  
  
```  
  
class CDebugReportHook  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDebugReportHook::CDebugReportHook](../Topic/CDebugReportHook::CDebugReportHook.md)|Вызовы [SetPipeName](../Topic/CDebugReportHook::SetPipeName.md), [SetTimeout](../Topic/CDebugReportHook::SetTimeout.md) и [SetHook](../Topic/CDebugReportHook::SetHook.md).|  
|[CDebugReportHook::~CDebugReportHook](../Topic/CDebugReportHook::~CDebugReportHook.md)|Вызовы [CDebugReportHook::RemoveHook](../Topic/CDebugReportHook::RemoveHook.md).|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDebugReportHook::CDebugReportHookProc](../Topic/CDebugReportHook::CDebugReportHookProc.md)|\(Статический\) Пользовательская функция отчетности, обрезается по среды выполнения c процесс отладки отчетов.|  
|[CDebugReportHook::RemoveHook](../Topic/CDebugReportHook::RemoveHook.md)|Вызовите этот метод, чтобы остановить отправлять для отладки отчеты к именованному каналу и восстановление предыдущего обработчик отчета.|  
|[CDebugReportHook::SetHook](../Topic/CDebugReportHook::SetHook.md)|Вызовите этот метод, чтобы отправлять для отладки отчеты к именованному каналу.|  
|[CDebugReportHook::SetPipeName](../Topic/CDebugReportHook::SetPipeName.md)|Вызывайте этот метод для задания компьютер и имя канала, к которой будут отправлены отчеты об отладке.|  
|[CDebugReportHook::SetTimeout](../Topic/CDebugReportHook::SetTimeout.md)|Вызовите этот метод, чтобы задать время в миллисекундах, в течение которого этот класс ожидает именованный канал.|  
  
## Заметки  
 Создайте экземпляр данного класса в отладочные построения пользовательских служб или приложений отправлять отладочные отчеты к именованному каналу.  Отчеты создаются путем вызова [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) debug или помощью программы\-оболочки для данной функции и макросы [ATLTRACE](../Topic/ATLTRACE%20\(ATL\).md)[ATLASSERT](../Topic/ATLASSERT.md).  
  
 Использование этого класса можно интерактивно для отладки компоненты, выполняющиеся в неинтерактивном [офис окна](http://msdn.microsoft.com/library/windows/desktop/ms687096).  
  
 Обратите внимание, отправлено отладки отчеты с использованием основной контекст безопасности потока.  Олицетворение временно отключен, что отладочные отчетов может быть доступна в ситуациях, когда производится олицетворение низких пользователей привилегий, как в веб\-приложении.  
  
## Требования  
 **Header:** atlutil.h  
  
## См. также  
 [Классы](../../atl/reference/atl-classes.md)