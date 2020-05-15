---
title: Сборки выпуска C++ — Visual Studio
ms.date: 12/10/2018
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
ms.openlocfilehash: 46ae5e0f3d545f0e3e004f612314ab416b270fd8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168828"
---
# <a name="release-builds"></a>Построения выпуска

В сборке выпуска используются оптимизации. При использовании оптимизации для создания сборки выпуска компилятор не будет создавать символьную отладочную информацию. Отсутствие символьной отладочной информации вместе с тем фактом, что для вызовов TRACE и ASSERT не создается код, означает, что размер исполняемого файла сокращается и, следовательно, выполняется быстрее.

## <a name="in-this-section"></a>Содержание раздела

[Распространенные проблемы, возникающие при создании сборок выпуска](common-problems-when-creating-a-release-build.md)<br/>
[Устранение проблем сборки выпуска](fixing-release-build-problems.md)<br/>
[Использование VERIFY вместо ASSERT](using-verify-instead-of-assert.md)<br/>
[Использование отладочной сборки для проверки перезаписи памяти](using-the-debug-build-to-check-for-memory-overwrite.md)<br/>
[Практическое руководство. Отладка сборки выпуска](how-to-debug-a-release-build.md)<br/>
[Проверка перезаписи памяти](checking-for-memory-overwrites.md)<br/>
[Оптимизация кода](optimizing-your-code.md)

## <a name="see-also"></a>См. также

[Справочные сведения о сборке C/C++](reference/c-cpp-building-reference.md)
