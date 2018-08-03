---
title: Использование setjmp-longjmp | Документация Майкрософт
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
ms.openlocfilehash: 2073729fc5445fc36e3d8a6f52c4f69b079c8b47
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462135"
---
# <a name="using-setjmplongjmp"></a>Использование setjmp/longjmp
Когда [setjmp](../c-runtime-library/reference/setjmp.md) и [longjmp](../c-runtime-library/reference/longjmp.md) при совместном использовании они предоставляют способ выполнения нелокального **goto**. Обычно они используются для передачи элемента управления выполнением в код обработки ошибок или восстановления в вызванной ранее подпрограмме без использования стандартных соглашений вызова или возврата.  
  
> [!CAUTION]
>  Тем не менее так как **setjmp** и **longjmp** не поддерживают семантику объектов C++, а так как они могут привести к снижению производительности, не позволяя оптимизировать локальные переменные, мы рекомендуем не использовать их в программах на C++. Мы рекомендуем использовать **попробуйте**/**catch** вместо конструкции.  
  
 Если вы решили использовать **setjmp**/**longjmp** в программы на языке C++, также включают \<setjmp.h > или \<setjmpex.h > Чтобы обеспечить правильное взаимодействие между функции и обработки исключений C++. Если вы используете [/EH](../build/reference/eh-exception-handling-model.md) для компиляции, деструкторы для локальных объектов вызываются во время очистки стека. Если вы используете **/EHs** для компиляции и один из функций вызывает функцию, которая использует [nothrow](../cpp/nothrow-cpp.md) и функцию, которая использует **nothrow** вызовы **longjmp**, а затем Очистка деструкторов может не произойти в зависимости от оптимизатора.  
  
 В переносимом коде при нелокального **goto** , который вызывает **longjmp** выполняется, правильное удаление объектов на основе кадров может быть ненадежным.  
  
## <a name="see-also"></a>См. также  
 [Сочетание исключений C (структурированные) и C++](../cpp/mixing-c-structured-and-cpp-exceptions.md)