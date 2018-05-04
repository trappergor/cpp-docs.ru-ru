---
title: Изменяемые данные-члены (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7dd639cbf1ef076dee6e447f317533bf12dae10
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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