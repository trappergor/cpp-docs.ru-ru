---
title: "CFtpConnection Class | Microsoft Docs"
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
  - "CFtpConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFtpConnection class"
  - "FTP (протокол передачи данных), установка подключений"
  - "Internet connections, FTP"
  - "Internet services, FTP"
ms.assetid: 5e3a0501-8893-49cf-a3d5-0628d8d6b936
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFtpConnection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Управляет подключение к серверу FTP через интернет и позволяет напрямую управлять каталогов и файлов на этом сервере.  
  
## Синтаксис  
  
```  
class CFtpConnection : public CInternetConnection  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFtpConnection::CFtpConnection](../Topic/CFtpConnection::CFtpConnection.md)|Создает объект `CFtpConnection`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFtpConnection::Command](../Topic/CFtpConnection::Command.md)|Отправляет команды непосредственно на FTP\-сервер.|  
|[CFtpConnection::CreateDirectory](../Topic/CFtpConnection::CreateDirectory.md)|Создает каталог на сервере.|  
|[CFtpConnection::GetCurrentDirectory](../Topic/CFtpConnection::GetCurrentDirectory.md)|Возвращает текущую папку для данного соединения.|  
|[CFtpConnection::GetCurrentDirectoryAsURL](../Topic/CFtpConnection::GetCurrentDirectoryAsURL.md)|Возвращает текущую папку в качестве url\-адреса для данного соединения.|  
|[CFtpConnection::GetFile](../Topic/CFtpConnection::GetFile.md)|Получает файл из подключенного сервера|  
|[CFtpConnection::OpenFile](../Topic/CFtpConnection::OpenFile.md)|Открытие файла на подключенном сервере.|  
|[CFtpConnection::PutFile](../Topic/CFtpConnection::PutFile.md)|Устанавливает файл на сервере.|  
|[CFtpConnection::Remove](../Topic/CFtpConnection::Remove.md)|Удаляет файл с сервера.|  
|[CFtpConnection::RemoveDirectory](../Topic/CFtpConnection::RemoveDirectory.md)|Удаляет заданный каталог с сервера.|  
|[CFtpConnection::Rename](../Topic/CFtpConnection::Rename.md)|Переименовывает файл на сервере.|  
|[CFtpConnection::SetCurrentDirectory](../Topic/CFtpConnection::SetCurrentDirectory.md)|Задает текущий каталог FTP.|  
  
## Заметки  
 FTP одну из 3 служб интернета, распознаваемых классами MFC WinInet.  
  
 Для связи с сервером через интернет по протоколу FTP, необходимо сначала создать экземпляр [CInternetSession](../Topic/CInternetSession%20Class.md), а затем создать объект `CFtpConnection`.  Никогда не создает объект `CFtpConnection` напрямую; вместо этого вызовите [CInternetSession::GetFtpConnection](../Topic/CInternetSession::GetFtpConnection.md), который создает и возвращает объект `CFtpConnection` указатель на него.  
  
 Дополнительные сведения о том, как `CFtpConnection` работает с другими классами MFC Интернета см. в статье [Устройств, используемые при программировании с WinInet](../../mfc/win32-internet-extensions-wininet.md).  Дополнительные сведения о связи с другими 2 широкое применение HTTP и gopher см. в разделе [CHttpConnection](../../mfc/reference/chttpconnection-class.md) классы и [CGopherConnection](../../mfc/reference/cgopherconnection-class.md).  
  
## Пример  
 См. пример в описании класса [CFtpFileFind](../Topic/CFtpFileFind%20Class.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CInternetConnection](../Topic/CInternetConnection%20Class.md)  
  
 `CFtpConnection`  
  
## Требования  
 **Header:**  afxinet.h  
  
## См. также  
 [CInternetConnection Class](../Topic/CInternetConnection%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Class](../Topic/CInternetConnection%20Class.md)   
 [CInternetSession Class](../Topic/CInternetSession%20Class.md)