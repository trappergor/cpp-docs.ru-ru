---
title: Изменяемые данные-члены (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a93ae14e6f630d8974163ce8295626a524b49e3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mutable-data-members-c"></a>Изменяемые члены данных (C++)
Это ключевое слово может применяться только к данным-членам класса, которые не являются статическими или константами. Если данные-член объявлены `mutable`, а затем можно присвоить значение этого элемента данных из **const** функции-члена.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
mutable member-variable-declaration;  
```  
  
## <a name="remarks"></a>Примечания  
 Например, следующий код компилируется без ошибок, поскольку член `m_accessCount` объявлен как `mutable`, и поэтому может изменяться функцией `GetFlag`, хотя функция `GetFlag` объявлена как постоянная функция-член.  
  
```  
// mutable.cpp  
class X  
{  
public:  
   bool GetFlag() const  
   {  
      m_accessCount++;  
      return m_flag;  
   }  
private:  
   bool m_flag;  
   mutable int m_accessCount;  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)