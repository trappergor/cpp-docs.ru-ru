---
title: "Класс type_index | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: typeindex/std::type_index
dev_langs: C++
helpviewer_keywords: type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b4b55118f4138da60a0b4a197b6ecc3f818441a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="typeindex-class"></a>Класс type_index
Класс `type_index` оборачивает указатель в [класс type_info](../cpp/type-info-class.md) для упрощения индексации такими объектами.  
  
class type_index { public: type_index(const type_info& tinfo); const char *name() const; size_t hash_code() const; bool operator==(const type_info& right) const; bool operator!=(const type_info& right) const; bool operator<(const type_info& right) const; bool operator\<=(const type_info& right) const; bool operator>(const type_info& right) const; bool operator>=(const type_info& right) const; };  
  
 Конструктор инициализирует `ptr` в `&tinfo`.  
  
 `name` возвращает `ptr->name()`.  
  
 `hash_code` возвращает `ptr->hash_code().`  
  
 `operator==` возвращает `*ptr == right.ptr`.  
  
 `operator!=` возвращает `!(*this == right)`.  
  
 `operator<` возвращает `*ptr->before(*right.ptr)`.  
  
 `operator<=` возвращает `!(right < *this).`  
  
 `operator>` возвращает `right < *this`.  
  
 `operator>=` возвращает `!(*this < right)`.  
  
## <a name="see-also"></a>См. также  
 [Сведения о типах среды выполнения](../cpp/run-time-type-information.md)   
 [\<typeindex>](../standard-library/typeindex.md)



