---
title: "Структура nothrow_t | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- nothrow_t
- std.nothrow_t
- std::nothrow_t
dev_langs:
- C++
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
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
translationtype: Machine Translation
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: b490cccf048b5d5b9be53508331cba89e66c952f
ms.lasthandoff: 02/24/2017

---
# <a name="nothrowt-structure"></a>Структура nothrow_t
Этот класс используется как параметр функции для оператора new, чтобы показать, что для сообщения об ошибке выделения памяти данная функция должна возвращать пустой указатель (NULL), а не вызывать исключение.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct std::nothrow_t {};
```  
  
## <a name="remarks"></a>Примечания  
 Структура помогает компилятору выбрать подходящую версию конструктора. [nothrow](../standard-library/new-functions.md#nothrow) является синонимом для объектов типа `std::nothrow_t`.  
  
## <a name="example"></a>Пример  
 См. разделы [operator new](../standard-library/new-operators.md#operator_new) и [operator new&#91;&#93;](../standard-library/new-operators.md#operator_new_arr) с примерами использования `std::nothrow_t` в качестве параметра функции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<new>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




