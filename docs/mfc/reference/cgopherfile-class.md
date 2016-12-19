---
title: "CGopherFile Class | Microsoft Docs"
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
  - "CGopherFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "класс CGopherFile"
  - "gopher protocol files"
  - "Интернет, gopher"
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGopherFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональные возможности для поиска и чтения файлов на сервер gopher.  
  
> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены нерекомендуемый, поскольку они не работают на платформе Windows XP, но они продолжат работать на предыдущих платформах.  
  
## Синтаксис  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## Члены  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CGopherFile::CGopherFile](../Topic/CGopherFile::CGopherFile.md)|Создает объект `CGopherFile`.|  
  
## Заметки  
 Служба gopher не позволяет пользователям к данным о записи к файлу gopher поскольку этот функций служб в основном в качестве меню\- управляемый интерфейс для поиска сведений.  Функции\-члены **Запись**, `WriteString` и `Flush``CGopherFile` не реализованы для `CGopherFile`.  Вызов этих функций в `CGopherFile` объект, передачи [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Дополнительные сведения о том, как `CGopherFile` работает с другими классами MFC Интернета см. в статье [Устройств, используемые при программировании с WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../Topic/CStdioFile%20Class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## Требования  
 **Header:**  afxinet.h  
  
## См. также  
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CInternetFile Class](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator Class](../Topic/CGopherLocator%20Class.md)   
 [CGopherFileFind Class](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection Class](../../mfc/reference/cgopherconnection-class.md)