---
title: Распространенные проблемы, возникающие при создании построений выпуска
ms.date: 11/04/2016
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
- troubleshooting release builds
- memory [C++], overwrites
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
ms.openlocfilehash: 9bd1cafe40417872d42f2e9e1427e5f2eccad7a7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328868"
---
# <a name="common-problems-when-creating-a-release-build"></a>Распространенные проблемы, возникающие при создании построений выпуска

Во время разработки, как правило, построить и протестировать с отладкой сборки вашего проекта. Если вы затем создаете приложение для сборки релиза, вы можете получить нарушение доступа.

В приведенном ниже списке показаны основные различия между отладкой и сборкой выпуска (nondebug). Есть и другие различия, но ниже приведены основные различия, которые могут привести к сбою приложения в сборке релиза, когда оно работает в сборке отладки.

- [Кучи Layout](#_core_heap_layout)

- [Компиляция](#_core_compilation)

- [Поддержка указателя](#_core_pointer_support)

- [Оптимизация](#_core_optimizations)

См. опцию компилятора для сборки отладки [(Catch Release-Build Errors in Dbug Build)](reference/gz-enable-stack-frame-run-time-error-checking.md) для получения информации о том, как улавливать ошибки сборки сборки релизов.

## <a name="heap-layout"></a><a name="_core_heap_layout"></a>Кучи Layout

Кучи макет будет причиной около девяносто процентов очевидных проблем, когда приложение работает в отладке, но не релиз.

При построении проекта для отладки используется отлажек памяти. Это означает, что все распределения памяти имеют охранник байты размещены вокруг них. Эти охранник байты обнаружить память перезаписи. Поскольку макет кучи отличается между версиями выпуска и отладки, перезапись памяти может не создавать никаких проблем в сборке отладки, но может иметь катастрофические последствия при сборке релиза.

Для получения дополнительной информации [см. Проверьте перезапись памяти](checking-for-memory-overwrites.md) и [используйте сборку Debug для проверки перезаписи памяти.](using-the-debug-build-to-check-for-memory-overwrite.md)

## <a name="compilation"></a><a name="_core_compilation"></a>Компиляции

Многие макросы MFC и большая часть реализации MFC изменяются при сборке для выпуска. В частности, макрос ASSERT ничего не оценивает в сборке релиза, поэтому ни один из кода, найденного в ASSERTs, не будет выполнен. Для получения дополнительной информации [см.](using-verify-instead-of-assert.md)

Некоторые функции встроены для увеличения скорости в сборке релиза. Оптимизация обычно включена в сборке релиза. Также используется другой разллеть памяти.

## <a name="pointer-support"></a><a name="_core_pointer_support"></a>Поддержка указателя

Отсутствие информации об отладке удаляет обивку из приложения. В сборке релиза, бродячие указатели имеют больше шансов указать на непреницизованную память вместо того, чтобы указывать на информацию об отладке.

## <a name="optimizations"></a><a name="_core_optimizations"></a>Оптимизации

В зависимости от характера определенных сегментов кода, оптимизирующий компилятор может генерировать неожиданный код. Это наименее вероятная причина проблем сборки релиза, но она возникает иногда. Для решения [см.](optimizing-your-code.md)

## <a name="see-also"></a>См. также раздел

[Сборки выпуска](release-builds.md)<br/>
[Исправление проблем сборки выпуска](fixing-release-build-problems.md)
