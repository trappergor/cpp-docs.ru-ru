---
title: Сборки выпуска C++ — Visual Studio
ms.date: 12/10/2018
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
ms.openlocfilehash: cf11e63354502be000ba5f7259d9e36dfa774060
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038167"
---
# <a name="release-builds"></a>Построения выпуска

Сборки выпуска использует оптимизации. При использовании оптимизации для создание сборки выпуска компилятор не выдает символьную отладочную информацию. Вызывает отсутствие символьную отладочную информацию, а также тот факт, что код не создается для ТРАССИРОВКИ и ASSERT, означает, что размер исполняемого файла уменьшается и будут выполняться быстрее.

## <a name="in-this-section"></a>Содержание раздела

[Распространенные проблемы, возникающие при создании построений выпуска](common-problems-when-creating-a-release-build.md)<br/>
[Устранение проблем построения выпуска](fixing-release-build-problems.md)<br/>
[Использование VERIFY вместо ASSERT](using-verify-instead-of-assert.md)<br/>
[Использование отладочного построения для проверки затирания памяти](using-the-debug-build-to-check-for-memory-overwrite.md)<br/>
[Практическое руководство. Отладка построения выпуска](how-to-debug-a-release-build.md)<br/>
[Проверка затирания памяти](checking-for-memory-overwrites.md)<br/>
[Оптимизация кода](optimizing-your-code.md)<br/>

## <a name="see-also"></a>См. также

[Ссылка на сборку C/C++](reference/c-cpp-building-reference.md)