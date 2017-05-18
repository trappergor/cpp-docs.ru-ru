---
title: "Структура bidirectional_iterator_tag | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xutility/std::bidirectional_iterator_tag
- bidirectional_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- bidirectional_iterator_tag class
- bidirectional_iterator_tag struct
ms.assetid: 9ac06066-b8ae-44b6-bee4-b05855f6a31a
caps.latest.revision: 20
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 33302a822cc36adf7f68d7cce29b678654aabb29
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="bidirectionaliteratortag-struct"></a>Структура bidirectional_iterator_tag
Класс, предоставляющий тип возвращаемого значения для функции **iterator_category**, которая представляет собой двунаправленный итератор.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct bidirectional_iterator_tag    : public forward_iterator_tag {};
```  
  
## <a name="remarks"></a>Примечания  
 Классы тегов категории используются как теги компиляции для выбора алгоритма. Функция шаблона должна найти наиболее точную категорию своего аргумента итератора, чтобы он мог использовать наиболее эффективный алгоритм во время компиляции. Для каждого итератора типа `Iterator`, `iterator_traits`< `Iterator`>:: **iterator_category** должна быть определена до наиболее точного тега категории, который описывает поведение итератора.  
  
 Тип является таким же, как **iterator**\< **Iter**>:: **iterator_category**, где **Iter** описывает объект, который может служить как двунаправленный итератор.  
  
## <a name="example"></a>Пример  
 Пример использования `bidirectional_iterator_tag` см. в разделе [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<iterator>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Структура forward_iterator_tag](../standard-library/forward-iterator-tag-struct.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




