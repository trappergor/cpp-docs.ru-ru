---
title: "conform | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "conform_CPP"
  - "vc-pragma.conform"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "conform - прагма"
  - "forScope conform - прагма"
  - "прагмы, conform"
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# conform
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к языку C\+\+**  
  
 Определяет поведение времени выполнения параметр компилятора [\/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md).  
  
## Синтаксис  
  
```  
#pragma conform(name [, show ] [, on | off ] [ [, push | pop ] [, identifier ] ] )  
```  
  
#### Параметры  
 *name*  
 Определяет имя параметра компилятора, которое требуется изменить.  Единственное допустимое *name* — это `forScope`.  
  
 **show** \(необязательно\)  
 Вызывает отображение текущей настройки *name* \(true или false\) посредством предупреждения во время компиляции.  Например, `#pragma conform(forScope, show)`.  
  
 **on, off** \(необязательно\)  
 Задание для параметра *name* значения **on** включает параметр компилятора [\/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md).  Значение по умолчанию — **off**.  
  
 **push** \(необязательно\)  
 Помещает текущее значение *name* во внутренний стек компилятора.  Если задан параметр *identifier*, можно задать помещение в стек значения **on** или **off** для параметра *name*.  Например, `#pragma conform(forScope, push, myname, on)`.  
  
 **pop** \(необязательно\)  
 Задает в качестве значения *name* значение вверху внутреннего стека компилятора, а затем извлекает данные из стека.  Если идентификатор определен с помощью параметра **pop**, стек будет извлекаться до тех пор, пока не будет найдена запись с параметром *identifier*, который также будет извлечен; текущее значение для *name* в следующей записи стека становится новым значением для параметра *name*.  Если задать извлечение данных с помощью параметра *identifier*, который не является записью в стеке, **pop** игнорируется.  
  
 *идентификатор* \(необязательно\)  
 Может быть включен с помощью команды **push** или **pop**.  Если используется *identifier*, можно также использовать описатель **on** или **off**.  
  
## Пример  
  
```  
// pragma_directive_conform.cpp  
// compile with: /W1  
// C4811 expected  
#pragma conform(forScope, show)  
#pragma conform(forScope, push, x, on)  
#pragma conform(forScope, push, x1, off)  
#pragma conform(forScope, push, x2, off)  
#pragma conform(forScope, push, x3, off)  
#pragma conform(forScope, show)  
#pragma conform(forScope, pop, x1)  
#pragma conform(forScope, show)  
  
int main() {}  
```  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)