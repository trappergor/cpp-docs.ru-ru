---
title: "Структура space_info | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: filesystem/std::tr2::sys::space_info
dev_langs: C++
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 50657e33becd0fb2dae94d515f82120d6a71e342
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="spaceinfo-structure"></a>Структура space_info
Содержит сведения о томе.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct space_info   {
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
    };  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|`unsigned long long available`|Представляет число байтов, доступных для представления данных в томе.|  
|`unsigned long long capacity`|Представляет общее число байтов, которое может представлять том.|  
|`unsigned long long free`|Представляет число байтов, не используемых для представления данных в томе.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<filesystem >  
  
 **Пространство имен:** std::experimental::filesystem  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [пробел](http://msdn.microsoft.com/en-us/7fce0b0e-523b-4598-b218-47245d0204ca)   
 [Навигация по файловой системе (C++)](../standard-library/file-system-navigation.md)

