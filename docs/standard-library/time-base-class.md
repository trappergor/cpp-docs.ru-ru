---
title: "Класс time_base | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: c1c7c6c708087827c853234dcbd4519c79fba2bf
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="timebase-class"></a>Класс time_base
Этот класс используется как базовый класс для аспектов класса шаблона time_get, указав только **dateorder** перечисляемого типа и несколько констант этого типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class time_base : public locale::facet {
public:
    enum dateorder {no_order,
    dmy,
 mdy,
    ymd,
 ydm};
    time_base(
 size_t _Refs = 0)
 ~time_base();

};
```  
  
## <a name="remarks"></a>Примечания  
 Каждая константа характеризует свой способ упорядочивания компонентов даты. Используются следующие константы:  
  
- **no_order** не задает никакого определенного порядка.  
  
- **dmy** задает порядок даты "день, месяц, год", как во "2 декабря 1979".  
  
- **mdy** задает порядок даты "месяц, день, год", как в "декабрь, 2, 1979".  
  
- **ymd** задает порядок даты "год, месяц, день", как в "1979/12/2".  
  
- **ydm** задает порядок даты "год, день, месяц", как в "1979: 2 декабря".  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




