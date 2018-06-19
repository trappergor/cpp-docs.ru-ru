---
title: Отладка и списки для встроенной сборки | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 457402626edcdb2be05923aa33bbd26b1cab7137
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050120"
---
# <a name="debugging-and-listings-for-inline-assembly"></a>Отладка и списки для встроенного кода на языке ассемблера
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Программы, содержащие встроенный код ассемблера, можно отлаживать с отладчик уровня источника, если компиляция выполняется с [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) параметр.  
  
 В отладчике можно установить точки останова в строках С, С++ и языка сборки. Если включить режим смешанной сборки и исходного кода, можно отобразить и исходный код, и код сборки в дизассемблированной форме.  
  
 Обратите внимание, что размещение нескольких инструкций сборки или операторов исходного языка на одной строке может помешать отладке. В режиме исходного кода можно воспользоваться отладчиком для установки точек останова на одной строке, но не в отдельных операторах одной и той же строки. Тот же принцип действует в отношении блока `__asm`, определенного как макрос С и расширяющегося до одной логической строки.  
  
 При создании смешанного исходного кода и сборки, список с [/FAs](../../build/reference/fa-fa-listing-file.md) параметр компилятора, список содержит формы источник и сборки каждой строки на языке ассемблера. Макросы не развернуты в списках, но они разворачиваются во время компиляции.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)