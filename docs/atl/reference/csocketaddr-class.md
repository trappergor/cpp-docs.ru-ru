---
title: "CSocketAddr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSocketAddr"
  - "ATL.CSocketAddr"
  - "ATL::CSocketAddr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSocketAddr class"
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSocketAddr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для преобразования имена узлов адреса узла, поддерживая как IPv4, так и формат IP ВЕРСИИ 6.  
  
## Синтаксис  
  
```  
  
class CSocketAddr  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSocketAddr::CSocketAddr](../Topic/CSocketAddr::CSocketAddr.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSocketAddr::FindAddr](../Topic/CSocketAddr::FindAddr.md)|Этот метод вызывается для преобразования предоставленное имя узла на адрес узла.|  
|[CSocketAddr::FindINET4Addr](../Topic/CSocketAddr::FindINET4Addr.md)|Вызовите этот метод, чтобы преобразовать имя узла IPv4 на адрес узла.|  
|[CSocketAddr::FindINET6Addr](../Topic/CSocketAddr::FindINET6Addr.md)|Вызовите этот метод, чтобы преобразовать имя узла IP версии 6 на адрес узла.|  
|[CSocketAddr::GetAddrInfo](../Topic/CSocketAddr::GetAddrInfo.md)|Вызовите этот метод, чтобы вернуть указатель к определенному элементу в списке **addrinfo**.|  
|[CSocketAddr::GetAddrInfoList](../Topic/CSocketAddr::GetAddrInfoList.md)|Вызовите этот метод, чтобы вернуть указатель на список **addrinfo**.|  
  
## Заметки  
 Этот класс обеспечивает подход к версии протокола IP агностический для поиска сетевого адреса для использования с программами\-оболочками функций API Windows и сокета sockets в библиотеках.  
  
 Члены этого класса, которые используются для поиска сетевого адреса используется функция Win32 API [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520).  
  
 Этот класс поддерживает оба сетевого адреса IPv4 andIPv6.  
  
## Требования  
 **Header:** atlsocket.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)