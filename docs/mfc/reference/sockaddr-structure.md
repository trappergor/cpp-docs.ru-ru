---
title: "Структура SOCKADDR | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SOCKADDR
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR structure
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: 12
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 28984fcc5614a5f901a01ffdeff4ea5f360f63fc
ms.lasthandoff: 02/24/2017

---
# <a name="sockaddr-structure"></a>Структура SOCKADDR
`SOCKADDR` Структура используется для хранения адреса протокола Интернета (IP) для компьютера, участвующих в связи сокеты Windows.  
  
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
 Максимальный размер всех структур сокета другой адрес.  
  
## <a name="remarks"></a>Примечания  
 Пакет разработчика Microsoft TCP/IP сокеты поддерживает только домены адрес Интернета. На самом деле вводить значения для каждого компонента адреса, используйте `SOCKADDR_IN` структуру данных, которая является специально для данного формата адреса. `SOCKADDR` И `SOCKADDR_IN` структур данных имеют одинаковый размер. Просто преобразовать для переключения между двумя структуру типов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** winsock2.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Структура SOCKADDR_IN](../../mfc/reference/sockaddr-in-structure.md)   
 [CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)   
 [CSocket::Create](../../mfc/reference/csocket-class.md#create)


