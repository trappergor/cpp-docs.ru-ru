---
title: Изменяемые данные-члены (C++) | Документация Майкрософт
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
ms.openlocfilehash: adc8f9c456d28089d57bc1f13b61ad8efa10b6b6
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402924"
---
# <a name="mutable-data-members-c"></a>Изменяемые члены данных (C++)
Это ключевое слово может применяться только к данным-членам класса, которые не являются статическими или константами. Если данные-член объявлены **изменяемый**, а затем можно присвоить значение этого элемента данных из **const** функция-член.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
mutable member-variable-declaration;  
```  
  
## <a name="remarks"></a>Примечания  
 Например, следующий код компилируется без ошибок, так как `m_accessCount` был объявлен **изменяемый**и поэтому могут быть изменены `GetFlag` несмотря на то что `GetFlag` является постоянная функция-член.  
  
```cpp 
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