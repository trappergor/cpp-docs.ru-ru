---
title: "Структура char_traits&lt;wchar_t&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a4cebf57b046cd01f5aa0ff9b8fee4897c573ae1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="chartraitsltwchartgt-struct"></a>Структура char_traits&lt;wchar_t&gt;
Класс, который является специализацией структуры шаблона **char_traits\<CharType>** к элементу типа `wchar_t`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <>  
struct char_traits<wchar_t>;
```  
  
## <a name="remarks"></a>Примечания  
 Специализация позволяет структуре использовать преимущества функций библиотеки, которые управляют объектами данного типа `wchar_t`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<string>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Структура char_traits](../standard-library/char-traits-struct.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



