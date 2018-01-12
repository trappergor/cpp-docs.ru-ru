---
title: "Использование стека | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 383f0072-0438-489f-8829-cca89582408c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d6e3aa8d01dcc85b6c37684ccccaf82c84d8dfb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="stack-usage"></a>Использование стека
Все памяти за пределами текущего адреса RSP считаются временными: операционная система или отладчик, могут быть перезаписаны эта память во время сеанса отладки пользователя или обработчик прерываний. Таким образом RSP всегда должен иметь значение перед попыткой чтения или записи значения в кадре стека.  
  
 В этом разделе описывается порядок выделения места в стеке для локальных переменных и **alloca** встроенная функция.  
  
-   [Выделение памяти в стеке](../build/stack-allocation.md)  
  
-   [Динамическое создание параметра области стека](../build/dynamic-parameter-stack-area-construction.md)  
  
-   [Типы функций](../build/function-types.md)  
  
-   [Выравнивание с помощью функции malloc](../build/malloc-alignment.md)  
  
-   [alloca](../build/alloca.md)  
  
## <a name="see-also"></a>См. также  
 [Программные соглашения для X64](../build/x64-software-conventions.md)