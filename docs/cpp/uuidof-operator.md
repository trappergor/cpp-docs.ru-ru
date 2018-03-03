---
title: "оператор __uuidof | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
dev_langs:
- C++
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c5d83f99b40e6eb897212fbcfb03c01b4f6b55e3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="uuidof-operator"></a>Оператор __uuidof
**Блок, относящийся только к системам Microsoft**  
  
 Извлекает идентификатор GUID, присоединенный к выражению.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      __uuidof (  
   expression   
)  
```  
  
## <a name="remarks"></a>Примечания  
 *Выражение* может быть имя типа, указатель, ссылку или массив этого типа, шаблон, специализированный для этих типов или переменную этого типа. Этот аргумент является допустимым, если компилятор может использовать его для поиска прикрепленного GUID.  
  
 Является особым случаем этой встроенной функции, если любой **0** или **NULL** , передается как аргумент. В этом случае оператор `__uuidof` возвращает GUID, состоящий из нулей.  
  
 Это ключевое слово позволяет извлечь GUID, прикрепленный к следующим объектам:  
  
-   Объект [uuid](../cpp/uuid-cpp.md) дополнительных атрибутов.  
  
-   Блок библиотеки создан с [модуль](../windows/module-cpp.md) атрибута.  
  
> [!NOTE]
>  В отладочной сборке ключевое слово `__uuidof` всегда инициализирует объект динамически (во время выполнения). В сборке выпуска ключевое слово `__uuidof` может инициализировать объект статически (во время компиляции).  
  
## <a name="example"></a>Пример  
 Следующий код (скомпилированный с библиотекой ole32.lib) будет выводить идентификатор uuid для блока библиотеки, созданного с атрибутом module.  
  
```  
// expre_uuidof.cpp  
// compile with: ole32.lib  
#include "stdio.h"  
#include "windows.h"  
  
[emitidl];  
[module(name="MyLib")];  
[export]  
struct stuff {  
   int i;  
};  
  
int main() {  
   LPOLESTR lpolestr;  
   StringFromCLSID(__uuidof(MyLib), &lpolestr);  
   wprintf_s(L"%s", lpolestr);  
   CoTaskMemFree(lpolestr);  
}  
```  
  
## <a name="comments"></a>Комментарии  
 В случаях, когда имя библиотеки больше не находится в области, можно использовать __LIBID\_ вместо `__uuidof`. Пример:  
  
```  
StringFromCLSID(__LIBID_, &lpolestr);  
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)