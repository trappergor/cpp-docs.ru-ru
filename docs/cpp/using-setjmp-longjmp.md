---
title: Использование setjmp и longjmp | Документация Майкрософт
ms.custom: ''
ms.date: 08/14/2018
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
ms.openlocfilehash: 711d829ea3393041c713fbb042318b680100a52a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111957"
---
# <a name="using-setjmp-and-longjmp"></a>Использование setjmp и longjmp

Когда [setjmp](../c-runtime-library/reference/setjmp.md) и [longjmp](../c-runtime-library/reference/longjmp.md) при совместном использовании они предоставляют способ выполнения нелокального **goto**. Они обычно используются в коде C для передачи управления выполнением в код обработки ошибок или восстановления в вызванной ранее подпрограмме без использования стандартных вызова соглашений или возврата.

> [!CAUTION]
> Так как `setjmp` и `longjmp` не поддерживают правильное удаление объектов кадра стека переносимо между компиляторы C++, а также могут снизить производительность, не позволяя оптимизировать локальные переменные, мы не рекомендуем использовать их в C++ программы. Мы рекомендуем использовать **попробуйте** и **catch** вместо конструкции.

Если вы решили использовать `setjmp` и `longjmp` в программы на языке C++, также включают \<setjmp.h > или \<setjmpex.h > Чтобы обеспечить правильное взаимодействие между функциями и исключением структурированную обработку исключений (SEH) или C++ Обработка.

**Блок, относящийся только к системам Microsoft**

Если вы используете [/EH](../build/reference/eh-exception-handling-model.md) для компиляции кода C++, то деструкторы для локальных объектов вызываются во время очистки стека. Тем не менее если вы используете **/EHs** или **/EHsc** для компиляции и одна из функций, которая использует [noexcept](../cpp/noexcept-cpp.md) вызовы `longjmp`, то деструктор раскрутки для этой функции может не произойти в зависимости от состояния оптимизатора.

В переносимом коде при `longjmp` вызов выполняется, со стандартом явным образом не гарантируется правильное удаление объектов на основе кадров и могут не поддерживаться другими компиляторами. Сообщить вам о пороге предупреждений 4, вызов `setjmp` вызывает предупреждение C4611: взаимодействие между «_setjmp» и деструктором объектов C++ не будет переносимым.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Сочетание исключений C (структурированные) и C++](../cpp/mixing-c-structured-and-cpp-exceptions.md)
