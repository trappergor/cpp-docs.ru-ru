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
- messages_base
- locale/std::messages_base
dev_langs:
- C++
helpviewer_keywords:
- messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
caps.latest.revision: 19
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 4e10582050f922e880577dc5a19d99a1ac03128e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

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




