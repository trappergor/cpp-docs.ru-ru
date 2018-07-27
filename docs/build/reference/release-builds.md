---
title: Построения выпуска | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3ae18c5e2dcdb735880509fd158dac4ccaa1462
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376654"
---
# <a name="release-builds"></a>Построения выпуска
Построение выпуска использует оптимизации. При использовании оптимизаций для создания построения выпуска компилятор не выдает символьную отладочную информацию. Вызывает отсутствие символьную отладочную информацию, а также тот факт, что код не создается для ТРАССИРОВКИ и ASSERT, означает, что размер исполняемого файла уменьшается и поэтому будет быстрее.  
  
 В этом разделе представлены сведения о, когда и почему может потребоваться изменить из отладочной сборки для сборки выпуска. Он также рассматриваются некоторые проблемы, которые могут возникнуть при изменении отладочной сборки выпуска:  
  
-   [Создание построения выпуска](../../build/reference/how-to-create-a-release-build.md)  
  
-   [Распространенные проблемы, возникающие при создании сборок выпуска](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
-   [Устранение проблем сборки выпуска](../../build/reference/fixing-release-build-problems.md)  
  
    -   [Изучение операторы ASSERT](../../build/reference/using-verify-instead-of-assert.md)  
  
    -   [Использование отладочного построения для проверки затирания памяти](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)  
  
    -   [Отладка построения выпуска](../../build/reference/how-to-debug-a-release-build.md)  
  
    -   [Проверка перезаписи памяти](../../build/reference/checking-for-memory-overwrites.md)  
  
## <a name="see-also"></a>См. также  
 [Построение проектов C++ в Visual Studio](../../ide/building-cpp-projects-in-visual-studio.md)   
 [Справочные сведения о сборке C/C++](../../build/reference/c-cpp-building-reference.md)