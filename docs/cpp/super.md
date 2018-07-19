---
title: __super | Документация Майкрософт
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
ms.openlocfilehash: b9caa3d08140887da45916b931b6a4850358db16
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944849"
---
# <a name="super"></a>__super
**Блок, относящийся только к системам Microsoft**  
  
 Позволяет явно указать, что для переопределяемой функции вызывается реализация из базового класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
__super::member_function();  
  
```  
  
## <a name="remarks"></a>Примечания  
 На этапе разрешения перегрузки учитываются все доступные методы базового класса, и вызывается функция, которая обеспечивает наилучшее совпадение.  
  
 **__super** может использоваться только в теле функции-члена.  
  
 **__super** нельзя использовать с помощью объявления. См. в разделе [объявление using](../cpp/using-declaration.md) Дополнительные сведения.  
  
 С появлением [атрибуты](../windows/cpp-attributes-reference.md) , внедряющих код, код может содержать один или несколько базовых классов, имена которых вы можете не знать, но которые содержат методы, которые должны вызываться.  
  
## <a name="example"></a>Пример  
  
```cpp 
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