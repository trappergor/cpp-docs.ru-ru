---
title: "CWaitCursor Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWaitCursor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "курсоры, wait cursor"
  - "CWaitCursor class"
  - "wait cursors"
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CWaitCursor Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет способ одн\- линии отображать курсор ожидания, который обычно отображается как часы, при выполнении длинномерную операцию.  
  
## Синтаксис  
  
```  
class CWaitCursor  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWaitCursor::CWaitCursor](../Topic/CWaitCursor::CWaitCursor.md)|Создает объект `CWaitCursor` и отображает курсор ожидания.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWaitCursor::Restore](../Topic/CWaitCursor::Restore.md)|Получает курсор ожидания после того, как он был изменен.|  
  
## Заметки  
 `CWaitCursor` не имеет базовый класс.  
  
 Хорошее Windows при программировании рекомендации необходимо указать курсор ожидания, когда выполняется операция, которая принимает заметное количество времени.  
  
 Для отображения курсора ожидания, просто укажите переменную `CWaitCursor` перед кодом, который выполняет длинномерную операцию.  Конструктор объекта курсор ожидания автоматически будет отображаться.  
  
 Если объект выходит из области \(в конце блока в котором объявлен объект `CWaitCursor` \), его деструктор задает курсор к предыдущему курсор.  Иначе говоря, объект автоматически выполняет необходимые операции очистки.  
  
> [!NOTE]
>  Из\-за, как их конструкторы и деструкторы, объекты `CWaitCursor` всегда объявлены как локальные переменные — они не объявлены как глобальные переменные и их выбранные с **новый**.  
  
 Если выполняется операция, которая может привести к тому, что курсор быть изменен, например отображение окна сообщения или диалогового окна, вызовите функцию\-член [восстановление](../Topic/CWaitCursor::Restore.md) для получения курсор ожидания.  Оно одобрен вызвать **Восстановить**, даже если курсор ожидания в данный момент отображается.  
  
 Другой способ отображения курсор ожидания использовать сочетание [CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md), [CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md) и возможности [CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md).  Однако `CWaitCursor` проще в использовании, поскольку нет необходимости устанавливать курсор к предыдущему курсор после завершения с длительной операцией.  
  
> [!NOTE]
>  MFC задает и получает курсор с помощью виртуальную функцию [CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md).  Можно переопределить эту функцию для предоставления пользовательской расширения функциональности.  
  
## Иерархия наследования  
 `CWaitCursor`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## Пример  
 [!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/CPP/cwaitcursor-class_1.cpp)]  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../Topic/CCmdTarget::BeginWaitCursor.md)   
 [CCmdTarget::EndWaitCursor](../Topic/CCmdTarget::EndWaitCursor.md)   
 [CCmdTarget::RestoreWaitCursor](../Topic/CCmdTarget::RestoreWaitCursor.md)   
 [CWinApp::DoWaitCursor](../Topic/CWinApp::DoWaitCursor.md)   
 [Инструкции: Измените курсор мыши в приложении Microsoft foundation class?](http://go.microsoft.com/fwlink/?LinkID=128044)