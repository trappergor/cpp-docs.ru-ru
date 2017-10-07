---
title: "Структура nothrow_t | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- nothrow_t
dev_langs:
- C++
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 1070820b63319cd3f08abbf3d5cd1adf02891cbb
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

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
 См. разделы [operator new](../standard-library/new-operators.md#op_new) и [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr) с примерами использования `std::nothrow_t` в качестве параметра функции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<new>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




