---
title: "CGopherConnection Class | Microsoft Docs"
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
  - "CGopherConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGopherConnection class"
  - "подключение к серверам"
  - "подключение к серверам, gopher servers"
  - "gopher - протокол"
  - "gopher server"
  - "Internet connections, gopher"
  - "Internet server, gopher"
  - "протоколы, gopher"
  - "серверы, подключение к"
  - "службы, gopher"
ms.assetid: b5b96aea-ac99-430e-bd84-d1372b43f78f
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGopherConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Управляет подключение к серверу через интернет gopher.  
  
> [!NOTE]
>  Классы `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` и их члены нерекомендуемый, поскольку они не работают на платформе Windows XP, но они продолжат работать на предыдущих платформах.  
  
## Синтаксис  
  
```  
class CGopherConnection : public CInternetConnection  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CGopherConnection::CGopherConnection](../Topic/CGopherConnection::CGopherConnection.md)|Создает объект `CGopherConnection`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CGopherConnection::CreateLocator](../Topic/CGopherConnection::CreateLocator.md)|Создает объект [CGopherLocator](../Topic/CGopherLocator%20Class.md) поиск файлов на сервер gopher.|  
|[CGopherConnection::GetAttribute](../Topic/CGopherConnection::GetAttribute.md)|Данные атрибута извлечение об объекте gopher.|  
|[CGopherConnection::OpenFile](../Topic/CGopherConnection::OpenFile.md)|Открывает файл gopher.|  
  
## Заметки  
 Служба gopher одну из 3 служб интернета, распознаваемых классами MFC WinInet.  
  
 Класс `CGopherConnection` содержит конструктор и 3 дополнительных функции\-члена, который управляет служба gopher. [OpenFile](../Topic/CGopherConnection::OpenFile.md), [CreateLocator](../Topic/CGopherConnection::CreateLocator.md) и [GetAttribute](../Topic/CGopherConnection::GetAttribute.md).  
  
 Для связи с сервером через интернет gopher, необходимо сначала создать экземпляр [CInternetSession](../Topic/CInternetSession%20Class.md), и затем вызовите [CInternetSession::GetGopherConnection](../Topic/CInternetSession::GetGopherConnection.md), который создает и возвращает объект `CGopherConnection` указатель на него.  Никогда не создает объект `CGopherConnection` напрямую.  
  
 Дополнительные сведения о том, как `CGopherConnection` работает с другими классами MFC Интернета см. в статье [Устройств, используемые при программировании с WinInet](../../mfc/win32-internet-extensions-wininet.md).  Дополнительные сведения об использовании других 2, поддерживаемых служб интернета, FTP и HTTP, см. классы [CHttpConnection](../../mfc/reference/chttpconnection-class.md) и [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CInternetConnection](../Topic/CInternetConnection%20Class.md)  
  
 `CGopherConnection`  
  
## Требования  
 **Header:**  afxinet.h  
  
## См. также  
 [CInternetConnection Class](../Topic/CInternetConnection%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFtpConnection Class](../../mfc/reference/cftpconnection-class.md)   
 [CHttpConnection Class](../../mfc/reference/chttpconnection-class.md)   
 [CInternetConnection Class](../Topic/CInternetConnection%20Class.md)   
 [CGopherLocator Class](../Topic/CGopherLocator%20Class.md)   
 [CGopherFile Class](../../mfc/reference/cgopherfile-class.md)   
 [CInternetSession Class](../Topic/CInternetSession%20Class.md)