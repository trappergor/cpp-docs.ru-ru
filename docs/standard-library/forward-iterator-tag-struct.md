---
title: "Структура forward_iterator_tag | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- forward_iterator_tag
- xutility/std::forward_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
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
ms.openlocfilehash: 659ada41e69a0d9d2ab90e80b60ea0b3e4546d3b
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="forwarditeratortag-struct"></a>Структура forward_iterator_tag
Класс, предоставляющий тип возвращаемого значения для функции **iterator_category**, которая представляет собой прямой итератор.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct forward_iterator_tag    : public input_iterator_tag {};
```  
  
## <a name="remarks"></a>Примечания  
 Классы тегов категории используются как теги компиляции для выбора алгоритма. Функция шаблона должна найти наиболее точно определенную категорию своего аргумента итератора, чтобы можно было использовать наиболее эффективный алгоритм во время компиляции. Для каждого итератора типа `Iterator` `iterator_traits`< `Iterator`> **::iterator_category** должна быть определена до наиболее точного тега категории, который описывает поведение итератора.  
  
 Тип является таким же, как **итератор**\< **Iter**> **::iterator_category**, когда **Iter** описывает объект, который может быть прямым итератором.  
  
## <a name="example"></a>Пример  
 См. в разделе [iterator_traits](../standard-library/iterator-traits-struct.md) или [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md) пример использования **iterator_tag**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<iterator>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Структура input_iterator_tag](../standard-library/input-iterator-tag-struct.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




