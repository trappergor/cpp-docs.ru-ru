---
title: Структура SOCKADDR_IN | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- SOCKADDR_IN
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR_IN structure [MFC]
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e5ec6ebf4329ff03c75240dc7cec93e9ba46331
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885742"
---
# <a name="sockaddrin-structure"></a>Структура SOCKADDR_IN
В семейство адресов Интернета `SOCKADDR_IN` структура используется Windows Sockets для указания адреса локальной или удаленной конечной точки, к которому осуществляется подключение к сокету.  
  
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
 Семейство адресов (должен быть AF_INET).  
  
 *sin_port*  
 IP-порт.  
  
 *sin_addr*  
 IP-адрес.  
  
 *Sin_Zero*  
 Заполнение, чтобы сделать структуру тот же размер, что `SOCKADDR`.  
  
## <a name="remarks"></a>Примечания  
 Это форма `SOCKADDR` структуры для семейства адресов Интернета и может быть приведен к `SOCKADDR`.  
  
 Компонент IP-адрес этой структуры имеет тип `IN_ADDR`. `IN_ADDR` Структура определена в файле заголовка Windows Sockets WINSOCK. H следующим образом:  
  
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
