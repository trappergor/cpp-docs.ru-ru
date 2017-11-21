---
title: "Выравнивание malloc | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a8d1d1b4-5122-456f-9a64-a50e105e55a5
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 66ec1e2e86996b8044909961bef9ab4ea3e76312
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="malloc-alignment"></a>Выравнивание с помощью функции malloc
[malloc](../c-runtime-library/reference/malloc.md) гарантирует возврат, выровнено для хранения любого объекта, которые используют основные выравнивание и умещалось объема памяти, выделенной памяти. Объект *фундаментальные выравнивание* является выравнивания, которое меньше или равно наибольшего выравнивания, поддерживаемого реализацией без указания выравнивания. (В Visual C++, это выравнивание, необходимого для `double`, или 8 байт. В коде для 64-разрядных платформ это ограничение составляет 16 байтов.) Например распределение четырехбайтовое расположения на границе, которая поддерживает любой объект 4 байта или меньше.  
  
 Visual C++ позволяет использовать типы, которые имеют *расширенных выравнивание*, который также называются *чрезмерно выравниваются* типы. Например, типы SSE [__m128](../cpp/m128.md) и `__m256`и типы, объявленные с помощью `__declspec(align( n ))` где `n` превышает 8, расширена выравнивания. Выравнивание памяти на границе, которая подходит для объекта, который требует расширенные выравнивания не гарантируется `malloc`. Чтобы выделить память для чрезмерно выровненные типы, используйте [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) и связанных функций.  
  
## <a name="see-also"></a>См. также  
 [Использование стека](../build/stack-usage.md)   
 [Выравнивание](../cpp/align-cpp.md)   
 [__declspec](../cpp/declspec.md)