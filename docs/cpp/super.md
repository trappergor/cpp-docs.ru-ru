---
title: __super | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- __super_cpp
dev_langs:
- C++
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 93585337ae34e7c95d1c11b0a970afc8b36987bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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