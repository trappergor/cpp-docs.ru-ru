---
title: Проблемы, возникающие при создании построений выпуска | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- unexpected code generation
- debugging [MFC], release builds
- release builds, troubleshooting
- stray pointers
- debug builds, difference from release builds
- MFC [C++], release builds
- heap layout problems
- pointers, stray
- release builds, building applications
- debug memory allocator
- optimization [C++], compiler
- projects [C++], debug configuration
- troubleshooting Visual C++
- troubleshooting release builds
- memory [C++], overwrites
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8860783a2cf9fb88b28e24e0bc16eb16c0dd5d77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="common-problems-when-creating-a-release-build"></a>Распространенные проблемы, возникающие при создании построений выпуска
Во время разработки обычно построение и тестирование отладочного построения проекта. При создании приложения для сборки выпуска, может возникнуть нарушение прав доступа.  
  
 Ниже перечислены основные различия между отладки и выпуска (построениями). Существуют другие различия, но ниже приведены основные различия, которые могут привести к сбою приложения в сборке выпуска, когда оно работает в отладочном построении.  
  
-   [Размещение в куче](#_core_heap_layout)  
  
-   [Компиляция](#_core_compilation)  
  
-   [Поддержка указателей](#_core_pointer_support)  
  
-   [Оптимизация](#_core_optimizations)  
  
 В разделе [/GZ (перехвата ошибок построения выпуска в отладочное построение)](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md) Дополнительные сведения о том, как перехватить выпуска ошибки построения в отладочных построениях.  
  
##  <a name="_core_heap_layout"></a> Размещение в куче  
 Структуры кучи будет причину около 90 процентов очевидной проблемы приложения, работающего в отладки, но не выпуск.  
  
 При построении проекта для отладки используется механизм распределения отладочной памяти. Это означает, что для всех операций выделения памяти иметь байты guard. Эти защитных байтов для обнаружения перезаписи памяти. Поскольку макет кучи отличается от выпуска и отладки версиях затирания памяти не может создать проблемы в отладочном построении, но может иметь последствия катастрофический в сборке выпуска.  
  
 Дополнительные сведения см. в разделе [проверки перезаписи памяти](../../build/reference/checking-for-memory-overwrites.md) и [использовать отладка сборки для проверки для перезаписи памяти](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md).  
  
##  <a name="_core_compilation"></a> Компиляция  
 Многие из макросов MFC и изменения реализации MFC при построении для выпуска. В частности макрос ASSERT имеет значение nothing в сборке выпуска, чтобы ни один код, содержащийся в будет выполняться. Дополнительные сведения см. в разделе [изучите операторы ASSERT](../../build/reference/using-verify-instead-of-assert.md).  
  
 Некоторые функции встраиваются в целях повышения производительности в окончательной сборке. Оптимизация обычно включаются в окончательную сборку. Кроме того, используется распределителя памяти по-другому.  
  
##  <a name="_core_pointer_support"></a> Поддержка указателей  
 Заполнение удаляет отсутствия отладочной информации из приложения. В сборке выпуска свободные указатели имеют больше шансов указывают на неинициализированной памяти, а не к отладочной информации.  
  
##  <a name="_core_optimizations"></a> Оптимизация  
 В зависимости от характера определенные сегменты кода оптимизирующий компилятор может создать непредвиденный код. Это наименее вероятная причина проблем построения выпуска, но возникают в некоторых случаях. Для решения, в разделе [оптимизация кода](../../build/reference/optimizing-your-code.md).  
  
## <a name="see-also"></a>См. также  
 [Построения выпуска](../../build/reference/release-builds.md)   
 [Устранение проблем сборки выпуска](../../build/reference/fixing-release-build-problems.md)