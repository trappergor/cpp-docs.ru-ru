---
title: __super | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __super_cpp
dev_langs:
- C++
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91ce48232884d1ab242ed52f82f614de058a2f91
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="super"></a>__super
**Блок, относящийся только к системам Microsoft**  
  
 Позволяет явно указать, что для переопределяемой функции вызывается реализация из базового класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
__super::  
member_function  
();  
  
```  
  
## <a name="remarks"></a>Примечания  
 На этапе разрешения перегрузки учитываются все доступные методы базового класса, и вызывается функция, которая обеспечивает наилучшее совпадение.  
  
 Ключевое слово `__super` может использоваться только в теле функции-члена.  
  
 Ключевое слово `__super` не может использоваться с объявлением using. В разделе [объявление using](../cpp/using-declaration.md) для получения дополнительной информации.  
  
 С появлением [атрибуты](../windows/cpp-attributes-reference.md) , внедряющих код, код может содержать один или несколько базовых классов, имена которых не всегда известно, но которые содержат методы, которые требуется вызвать.  
  
## <a name="example"></a>Пример  
  
```  
// deriv_super.cpp  
// compile with: /c  
struct B1 {  
   void mf(int) {}  
};  
  
struct B2 {  
   void mf(short) {}  
  
   void mf(char) {}  
};  
  
struct D : B1, B2 {  
   void mf(short) {  
      __super::mf(1);   // Calls B1::mf(int)  
      __super::mf('s');   // Calls B2::mf(char)  
   }  
};  
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)