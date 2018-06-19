---
title: Использование setjmp longjmp | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- longjmp_cpp
- setjmp_cpp
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- setjmpex.h
- longjmp function in C++ programs
- setjmp.h
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dee79d5b81e968e89e8072fb545c86f33be9bcce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422609"
---
# <a name="using-setjmplongjmp"></a>Использование setjmp/longjmp
Когда [setjmp](../c-runtime-library/reference/setjmp.md) и [longjmp](../c-runtime-library/reference/longjmp.md) будут использоваться совместно, они предоставляют способ выполнения нелокального `goto`. Обычно они используются для передачи элемента управления выполнением в код обработки ошибок или восстановления в вызванной ранее подпрограмме без использования стандартных соглашений вызова или возврата.  
  
> [!CAUTION]
>  Однако, поскольку `setjmp` и `longjmp` не поддерживают семантику объектов C++, а также могут снизить производительность, не позволяя оптимизировать локальные переменные, использовать их в программах на C++ не рекомендуется. Мы рекомендуем использовать `try` / `catch` вместо конструкции.  
  
 Если вы решили использовать `setjmp` / `longjmp` в программе на C++, следует также включить \<setjmp.h > или \<setjmpex.h > Чтобы обеспечить правильное взаимодействие между функциями и обработка исключений с ++. Если вы используете [/EH](../build/reference/eh-exception-handling-model.md) для компиляции, деструкторы для локальных объектов вызываются во время очистки стека. Если вы используете **/EHs** для компиляции и одной из функций вызывает функцию, которая использует [nothrow](../cpp/nothrow-cpp.md) и функцию, которая использует `nothrow` вызовы `longjmp`, деструкторов может не произойти, а затем в зависимости от оптимизатора.  
  
 В переносимом коде при выполнении нелокального оператора `goto`, вызывающего `longjmp`, правильное удаление основанных на кадре объектов может быть ненадежным.  
  
## <a name="see-also"></a>См. также  
 [Сочетание исключений C (структурированные) и C++](../cpp/mixing-c-structured-and-cpp-exceptions.md)