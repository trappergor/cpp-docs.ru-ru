---
title: "соответствует | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- conform_CPP
- vc-pragma.conform
dev_langs:
- C++
helpviewer_keywords:
- conform pragma
- forScope conform pragma
- pragmas, conform
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 476228dc1331d005e4886c905256fad23353874c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="conform"></a>conform
**Конкретных C++**  
  
 Задает поведение времени выполнения [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) параметр компилятора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma conform(name [, show ] [, on | off ] [ [, push | pop ] [, identifier ] ] )  
```  
  
#### <a name="parameters"></a>Параметры  
 *name*  
 Определяет имя параметра компилятора, которое требуется изменить. Единственным допустимым *имя* — `forScope`.  
  
 **Показать** (необязательно)  
 Вызывает текущий параметр *имя* (true или false), для отображения посредством предупреждения во время компиляции. Например, `#pragma conform(forScope, show)`.  
  
 **Вкл., Выкл**(необязательно)  
 Установка *имя* для **на** позволяет [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) параметр компилятора. Значение по умолчанию — **off**.  
  
 **Принудительная** (необязательно)  
 Помещает текущее значение *имя* на внутреннем стеке компилятора. При указании *идентификатор*, можно указать **на** или **off** значение для *имя* для помещается в стек. Например, `#pragma conform(forScope, push, myname, on)`.  
  
 **POP** (необязательно)  
 Задает значение *имя* значение вверху внутреннего стека компилятора, а затем извлекает данные из стека. Если идентификатор определен с помощью **pop**, стек будет извлекаться обратно в том случае, пока найдет запись с *идентификатор*, который также будет извлечен; текущее значение для *имя* в следующей записи стека становится новым значением для *имя*. Если задать извлечение данных с *идентификатор* , не является запись в стеке, **pop** игнорируется.  
  
 *Идентификатор*(необязательно)  
 Может быть включен с **принудительной** или **pop** команды. Если *идентификатор* используется, то **на** или **off** также можно использовать спецификатор.  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)