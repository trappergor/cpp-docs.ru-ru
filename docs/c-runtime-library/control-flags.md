---
title: "Флаги управления | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 9e8d2030edb3c048ec67ddd5a7b0782d2bbfdd9a
ms.lasthandoff: 02/24/2017

---
# <a name="control-flags"></a>Флаги управления
Отладочная версия библиотеки времени выполнения Microsoft C использует следующие флаги для управления выделением памяти в куче и процессом создания отчетов. Дополнительные сведения см. в статье [Методы отладки CRT](/visualstudio/debugger/crt-debugging-techniques).  
  
|Flag|Описание|  
|----------|-----------------|  
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Сопоставляет основные функции кучи и их отладочные версии|  
|[_DEBUG](../c-runtime-library/debug.md)|Позволяет использовать отладочные версий функций среды выполнения|  
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Контролирует способ отслеживания выделения памяти отладочным диспетчером кучи|  
  
 Эти флаги можно определить с помощью параметра командной строки /D или с помощью директивы `#define`. Если этот флаг определяется с помощью директивы `#define`, она должна предшествовать оператору включения заголовочного файла, содержащего объявления подпрограмм.  
  
## <a name="see-also"></a>См. также  
 [Глобальные переменные и стандартные типы](../c-runtime-library/global-variables-and-standard-types.md)
