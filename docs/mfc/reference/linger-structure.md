---
title: "Структура LINGER | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LINGER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LINGER - структура"
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура LINGER
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `LINGER` используется для управления параметры **SO\_LINGER** и **SO\_DONTLINGER**`CAsyncSocket::GetSockOpt`.  
  
## Синтаксис  
  
```  
  
      struct linger {  
   u_short l_onoff;            // option on/off  
   u_short l_linger;           // linger time  
};  
```  
  
## Заметки  
 Задание параметра **SO\_DONTLINGER** предотвращает блокировку на функцию\-член **Закрыть** во время ожидания unsent данные, которые необходимо отправить.  Устанавливать этот параметр эквивалентен параметр **SO\_LINGER** с **l\_onoff** установите значение 0.  
  
## Требования  
 **Заголовок:** winsock2.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../Topic/CAsyncSocket::GetSockOpt.md)   
 [CAsyncSocket::SetSockOpt](../Topic/CAsyncSocket::SetSockOpt.md)