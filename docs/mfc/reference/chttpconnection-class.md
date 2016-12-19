---
title: "CHttpConnection Class | Microsoft Docs"
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
  - "CHttpConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHttpConnection class"
  - "подключение к серверам"
  - "подключение к серверам, HTTP-серверы"
  - "подключения [C++], HTTP"
  - "подключения HTTP"
  - "HTTP-серверы, подключение к"
  - "Internet connections, HTTP"
  - "Internet protocols"
  - "Internet protocols, HTTP"
  - "Internet server, HTTP"
  - "протоколы, HTTP"
  - "серверы, подключение к"
ms.assetid: a402b662-c445-4988-800d-c8278551babe
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHttpConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Управляет подключение к HTTP\-серверу.  
  
## Синтаксис  
  
```  
class CHttpConnection : public CInternetConnection  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHttpConnection::CHttpConnection](../Topic/CHttpConnection::CHttpConnection.md)|Создает объект `CHttpConnection`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CHttpConnection::OpenRequest](../Topic/CHttpConnection::OpenRequest.md)|Открывает HTTP\-запроса.|  
  
## Заметки  
 HTTP один из 3 серверных протоколов Интернета, реализованную классами MFC WinInet.  
  
 Класс `CHttpConnection` содержит конструктор и один функции\-члена, [OpenRequest](../Topic/CHttpConnection::OpenRequest.md), который управляет подключения к серверу с помощью протокола HTTP.  
  
 Для взаимодействия с HTTP\-сервера необходимо сначала создать экземпляр [CInternetSession](../Topic/CInternetSession%20Class.md), а затем создать объект [CHttpConnection](#_mfc_chttpconnection).  Никогда не создает объект `CHttpConnection` напрямую; вместо этого вызовите [CInternetSession::GetHttpConnection](../Topic/CInternetSession::GetHttpConnection.md), который создает и возвращает объект `CHttpConnection` указатель на него.  
  
 Дополнительные сведения о том, как `CHttpConnection` работает с другими классами MFC Интернета см. в статье [Устройств, используемые при программировании с WinInet](../../mfc/win32-internet-extensions-wininet.md).  Дополнительные сведения о подключении к серверам с помощью других поддерживаемых протоколов Интернета, gopher 2 и FTP, см. классы [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) и [CFtpConnection](../../mfc/reference/cftpconnection-class.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CInternetConnection](../Topic/CInternetConnection%20Class.md)  
  
 `CHttpConnection`  
  
## Требования  
 **Header:**  afxinet.h  
  
## См. также  
 [CInternetConnection Class](../Topic/CInternetConnection%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../Topic/CInternetConnection%20Class.md)   
 [CHttpFile Class](../Topic/CHttpFile%20Class.md)