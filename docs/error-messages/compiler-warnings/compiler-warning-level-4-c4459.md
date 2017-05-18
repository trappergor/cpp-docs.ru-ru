---
title: "Предупреждение (уровень 4) C4459 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4459
dev_langs:
- C++
helpviewer_keywords:
- C4459
ms.assetid: ee9f6287-9c70-4b10-82a0-add82a13997f
caps.latest.revision: 0
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 87550474065639f6e1c7521ebfe76792d748ce9b
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4459"></a>Компилятор C4459 предупреждение (уровень 4)
  
> объявление "*идентификатор*" скрывает глобальное объявление
  
Объявление *идентификатор* в локальной области видимости скрывает объявление с идентичными именами *идентификатор* в глобальной области видимости. Это предупреждение позволяет узнать, который ссылается на *идентификатор* в этой области разрешается локально объявленных версии, а не глобальных версия, которая может быть или не быть намерениям. Как правило рекомендуется свести к минимуму использование глобальных переменных в качестве хорошей практикой реконструирования. Чтобы свести к минимуму засорения глобального пространства имен, рекомендуется использование именованного пространства имен для глобальных переменных.  
  
Это предупреждение впервые появился в Visual Studio 2015, в Visual C++ версии компилятора 18.00. Чтобы подавить предупреждения, связанные с этой версии компилятора или более поздней версии, при переносе кода, используйте [/wv: 18](../../build/reference/compiler-option-warning-level.md) параметр компилятора. 

## <a name="example"></a>Пример
  
 Следующий пример приводит к возникновению ошибки C4459:  
  
```cpp  
// C4459_hide.cpp
// compile with: cl /W4 /EHsc C4459_hide.cpp
int global_or_local = 1;

int main() { 
    int global_or_local; // warning C4459 
    global_or_local = 2;
} 
```  
  
Один из способов устранения этой проблемы является создание пространства имен для вашего globals, но не использовать `using` директивы для переноса этого пространства имен в области видимости, все ссылки должны использовать однозначным полные имена:  
  
```cpp  
// C4459_namespace.cpp
// compile with: cl /W4 /EHsc C4459_namespace.cpp
namespace globals {
    int global_or_local = 1;
}

int main() { 
    int global_or_local; // OK 
    global_or_local = 2;
    globals::global_or_local = 3;
} 
```  

