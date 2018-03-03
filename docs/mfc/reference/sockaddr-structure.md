---
title: "Структура SOCKADDR | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SOCKADDR
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR structure [MFC]
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 55b310ec83aae35c7386d61849663752811651d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="sockaddr-structure"></a>Структура SOCKADDR
`SOCKADDR` Структура используется для хранения адреса протокола Интернета (IP) для компьютера, участвующие в связи сокеты Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct sockaddr {  
    unsigned short sa_family;  
    char sa_data[14];  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 *sa_family*  
 Семейство адресов сокета.  
  
 *sa_data*  
 Максимальный размер всех структур адрес различных сокетов.  
  
## <a name="remarks"></a>Примечания  
 Пакет средств разработки Microsoft TCP/IP сокеты поддерживает только адреса доменов Интернета. Фактически вводить значения для каждой части адреса, используйте `SOCKADDR_IN` структуру данных, которая предназначена для этот формат адреса. `SOCKADDR` И `SOCKADDR_IN` структур данных имеют одинаковый размер. Просто преобразовать для переключения между двумя структуру типов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winsock2.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Структура SOCKADDR_IN](../../mfc/reference/sockaddr-in-structure.md)   
 [CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)   
 [CSocket::Create](../../mfc/reference/csocket-class.md#create)

