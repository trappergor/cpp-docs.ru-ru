---
title: "Отладка и списки для встроенной сборки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fea943c30d48ac122ae5d848306e4fe251f58da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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