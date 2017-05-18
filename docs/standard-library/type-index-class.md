---
title: "Класс type_index | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- typeindex/std::type_index
dev_langs:
- C++
helpviewer_keywords:
- type_index class
ms.assetid: db366119-74cb-43e8-aacf-9679e561fa2f
caps.latest.revision: 14
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: ca921a28653cf83cd76f4d8e826af277f1f574e1
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

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




