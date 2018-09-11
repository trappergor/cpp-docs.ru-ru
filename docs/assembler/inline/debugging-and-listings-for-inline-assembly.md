---
title: Отладка и списки для встроенной сборки | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- source level debugger
- __asm keyword [C++], debugging
- inline assembly, listings
- bugs, __asm blocks
- debugging [C++], inline assembly code
- inline assembly, debugging
ms.assetid: 69266930-6f9a-433d-b704-f4f44e7b2583
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6cca954ae15252b97d883ba8491fdb98e506f68
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689293"
---
# <a name="debugging-and-listings-for-inline-assembly"></a>Отладка и списки для встроенного кода на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Если компиляция выполняется с помощью программы, содержащие встроенный код ассемблера можно отлаживать отладчик уровня исходного [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) параметр.

В отладчике можно установить точки останова в строках С, С++ и языка сборки. Если включить режим смешанной сборки и исходного кода, можно отобразить и исходный код, и код сборки в дизассемблированной форме.

Обратите внимание, что размещение нескольких инструкций сборки или операторов исходного языка на одной строке может помешать отладке. В режиме исходного кода можно воспользоваться отладчиком для установки точек останова на одной строке, но не в отдельных операторах одной и той же строки. Тот же принцип действует в отношении блока `__asm`, определенного как макрос С и расширяющегося до одной логической строки.

При создании смешанных источник, а список с помощью сборок [параметра/FAs](../../build/reference/fa-fa-listing-file.md) параметр компилятора, список содержит forms исходном, так и сборки каждой строки языка ассемблера. Макросы не развернуты в списках, но они разворачиваются во время компиляции.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>