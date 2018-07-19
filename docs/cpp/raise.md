---
title: __raise | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __raise
- __raise_cpp
dev_langs:
- C++
helpviewer_keywords:
- __raise keyword [C++]
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a95f012b36e30c171fde1cbc8d28a21a074e281
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944226"
---
# <a name="raise"></a>__raise
Выделяет место вызова события.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
__raise method-declarator;  
  
```  
  
## <a name="remarks"></a>Примечания  
 Событие из управляемого кода можно вызвать только в пределах класса, где оно определено. См. в разделе [событий](../windows/event-cpp-component-extensions.md) Дополнительные сведения.  
  
 Ключевое слово **__raise** вызывает ошибку, которая возникает при вызове непредвиденных событий.  
  
> [!NOTE]
>  Класс-шаблон или структура не могут содержать события.  
  
## <a name="example"></a>Пример  
  
```cpp 
// EventHandlingRef_raise.cpp  
struct E {  
   __event void func1();  
   void func1(int) {}  
  
   void func2() {}  
  
   void b() {  
      __raise func1();  
      __raise func1(1);  // C3745: 'int Event::bar(int)':   
                         // only an event can be 'raised'  
      __raise func2();   // C3745  
   }  
};  
  
int main() {  
   E e;  
   __raise e.func1();  
   __raise e.func1(1);  // C3745  
   __raise e.func2();   // C3745  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Обработка событий](../cpp/event-handling.md)   
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)