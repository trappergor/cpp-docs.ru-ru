---
title: "Структура SOCKADDR_IN | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SOCKADDR_IN
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR_IN structure
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 77ed806bc6afc7ba02663a19a724541bbe0dae42
ms.lasthandoff: 02/24/2017

---
# <a name="sockaddrin-structure"></a>Структура SOCKADDR_IN
В операционных системах семейства адресов Интернета `SOCKADDR_IN` Windows Sockets использовать структуру, чтобы указать адрес локальной или удаленной конечной точки, к которому осуществляется подключение сокета.  
  
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
 Это форма `SOCKADDR` структуры для семейства адресов Интернета и может быть приведен к `SOCKADDR`.  
  
 Компонент IP-адрес из этой структуры имеет тип **инет_адрес**. **Инет_адрес** структура определена в заголовочном файле Windows Sockets WINSOCK. H следующим образом:  
  
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

