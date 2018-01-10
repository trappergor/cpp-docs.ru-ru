---
title: "Структура SOCKADDR_IN | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SOCKADDR_IN
dev_langs: C++
helpviewer_keywords: SOCKADDR_IN structure [MFC]
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e5350e48570a564361328e7b666a1cbb976221a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="sockaddrin-structure"></a>Структура SOCKADDR_IN
В операционных системах семейства адресов Интернета `SOCKADDR_IN` Windows Sockets использовать структуру для указания адреса локальной или удаленной конечной точки для подключения сокета.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct sockaddr_in{  
    short sin_family;  
    unsigned short sin_port;  
struct in_addr sin_addr;  
    char sin_zero[8];  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 *sin_family*  
 Семейство адресов (должно быть **AF_INET**).  
  
 *sin_port*  
 IP-порт.  
  
 *sin_addr*  
 IP-адрес.  
  
 *Sin_Zero*  
 Дополнения, чтобы сделать структуру совпадает с размером `SOCKADDR`.  
  
## <a name="remarks"></a>Примечания  
 Это является формой `SOCKADDR` структуры для семейства адресов Интернета и может быть приведен к `SOCKADDR`.  
  
 Компонент IP адреса этой структуры имеет тип **инет_адрес**. **Инет_адрес** структура определена в файле заголовка Windows Sockets WINSOCK. H следующим образом:  
  
```  
struct in_addr {
    union {
        struct {  
            unsigned char s_b1, s_b2, s_b3, s_b4;  
        } S_un_b;  
        struct {  
            unsigned short s_w1, s_w2;
        } S_un_w;
        unsigned long S_addr;
    } S_un;  
};  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winsock2.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Структура SOCKADDR](../../mfc/reference/sockaddr-structure.md)
