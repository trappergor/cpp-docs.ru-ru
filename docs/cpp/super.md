---
title: "__super | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __super_cpp
- __super
dev_langs:
- C++
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 64600f8cf642b0c7906873a73aa4da41897a57f5
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="super"></a>__super
**Блок, относящийся только к системам Майкрософт**  
  
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
