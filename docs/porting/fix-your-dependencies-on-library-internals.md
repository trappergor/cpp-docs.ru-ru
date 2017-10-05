---
title: "Исправление зависимостей от внутренних компонентов библиотеки | Microsoft Docs"
ms.custom: 
ms.date: 05/24/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- library internals in an upgraded Visual C++ project
- _Hash_seq in an upgraded Visual C++ project
ms.assetid: 493e0452-6ecb-4edc-ae20-b6fce2d7d3c5
caps.latest.revision: 1
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: e775744188a895a11c09de03848f621b6e3ecee8
ms.openlocfilehash: c2cc376776b79b4a20d8d98e9d97a56db008d433
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="fix-your-dependencies-on-library-internals"></a>Исправление зависимостей от внутренних компонентов библиотеки

Корпорация Майкрософт опубликовала исходный код для стандартной библиотеки, большей части библиотеки времени выполнения C и других библиотек Майкрософт в целом ряде версий Visual Studio. Мы сделали это для того, чтобы вы могли лучше понимать работу библиотеки и эффективнее отлаживать свой код. Одним из побочных эффектов публикации исходного кода библиотеки является то, что вам предоставляются некоторые внутренние значения, структуры данных и функции, которые не являются частью интерфейса библиотеки. Их имена обычно начинаются с двух символов подчеркивания или символа подчеркивания и прописной буквы, и они являются в стандарте C++ зарезервированными. Эти значения, структуры и функции используются в реализации библиотек и по мере развития библиотек могут изменяться, поэтому настоятельно рекомендуется не создавать от них зависимостей. В противном случае вы рискуете получить непереносимый код и проблемы при переводе кода на новые версии библиотек.  

В большинстве случаев изменения во внутренних компонентах библиотек не указываются в документах о новых возможностях и критических изменениях для каждого выпуска Visual Studio. Ведь, вообще говоря, эти детали реализации не должны вас касаться. Но иногда слишком велик соблазн использовать какой-то код внутри библиотеки. В этом разделе рассматриваются зависимости от внутренних компонентов библиотеки времени выполнения C и стандартной библиотеки C++. Кроме того, вы узнаете, как удалить эти зависимости из вашего кода, чтобы улучшить его переносимость или перевести его на новые версии библиотеки.

## <a name="hashseq"></a>_Hash_seq  

Внутренняя хэш-функция `std::_Hash_seq(const unsigned char *, size_t)`, используемая для реализации `std::hash` в некоторых строковых типах, отображалась в последних версиях стандартной библиотеки. Эта функция применяла [хэш-алгоритм FNV-1a]( https://en.wikipedia.org/wiki/Fowler%E2%80%93Noll%E2%80%93Vo_hash_function) к последовательности символов.  
  
Существует два способа удаления этой зависимости.  

-   Если вам нужно поместить последовательность `const char *` в неупорядоченный контейнер, используя тот же механизм хэш-кода, что и `basic_string`, воспользуйтесь перегрузкой шаблона `std::hash`, который принимает `std::string_view`, чтобы получить этот хэш-код в переносимом виде. Пока нельзя сказать точно, будет ли код библиотеки для работы со строками по-прежнему опираться на хэш-функцию FNV-1a в будущем. Поэтому лучше всего избегать зависимости от этого конкретного хэш-алгоритма, используя предложенный здесь способ. 
  
-   Если вы хотите применить хэш FNV-1a к произвольному набору памяти, мы выложили этот код в GitHub-репозитории [VCSamples]( https://github.com/Microsoft/vcsamples) в виде автономного файла заголовка [fnv1a.hpp](https://github.com/Microsoft/VCSamples/tree/master/VC2015Samples/_Hash_seq) по [лицензии MIT](https://github.com/Microsoft/VCSamples/blob/master/license.txt). Для вашего удобства приводим этот код здесь. Вы можете скопировать этот код в файл заголовка, добавить заголовок в любой затронутый код, а затем найти и заменить все случаи `_Hash_seq` на `fnv1a_hash_bytes`. Поведение будет идентично внутренней реализации в `_Hash_seq`. 

```cpp  
/*
VCSamples
Copyright (c) Microsoft Corporation
All rights reserved. 
MIT License
Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED *AS IS*, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
*/
#include <stddef.h>

inline size_t fnv1a_hash_bytes(const unsigned char * first, size_t count) {
#if defined(_WIN64)
    static_assert(sizeof(size_t) == 8, "This code is for 64-bit size_t.");
    const size_t fnv_offset_basis = 14695981039346656037ULL;
    const size_t fnv_prime = 1099511628211ULL;

#else /* defined(_WIN64) */
    static_assert(sizeof(size_t) == 4, "This code is for 32-bit size_t.");
    const size_t fnv_offset_basis = 2166136261U;
    const size_t fnv_prime = 16777619U;
#endif /* defined(_WIN64) */

    size_t result = fnv_offset_basis;
    for (size_t next = 0; next < count; ++next)
        {   // fold in another byte
        result ^= (size_t)first[next];
        result *= fnv_prime;
        }
    return (result);
}
```  
  
## <a name="see-also"></a>См. также  
  
[Обновление проектов, созданных в предыдущих версиях Visual C++](upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
[Общие сведения о возможных проблемах, возникающих при обновлении (Visual C++)](overview-of-potential-upgrade-issues-visual-cpp.md)  
[Обновление кода для универсальной среды выполнения](upgrade-your-code-to-the-universal-crt.md)  

