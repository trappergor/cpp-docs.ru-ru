---
title: "Класс messages_base | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocmes/std::messages_base
dev_langs:
- C++
helpviewer_keywords:
- messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: e95f92d910919ed0fc07943ff7b452ddd7d6b203
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="messagesbase-class"></a>Класс messages_base
Базовый класс, описывающий тип `int` для каталога сообщений.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct messages_base : locale::facet {
    typedef int catalog;
    explicit messages_base(size_t _Refs = 0)
};
```  
  
## <a name="remarks"></a>Примечания  
 Тип каталога является синонимом типа `int`, который описывает возможные возвращаемые значения сообщений:: [do_open](../standard-library/messages-class.md#do_open).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




