---
title: "Флаги управления | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.flags
dev_langs: C++
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71e0b1d01e291a1fa48740ccb6389a1b064433b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="control-flags"></a>Флаги управления
Отладочная версия библиотеки времени выполнения Microsoft C использует следующие флаги для управления выделением памяти в куче и процессом создания отчетов. Дополнительные сведения см. в статье [Методы отладки CRT](/visualstudio/debugger/crt-debugging-techniques).  
  
|Flag|Описание:|  
|----------|-----------------|  
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Сопоставляет основные функции кучи и их отладочные версии|  
|[_DEBUG](../c-runtime-library/debug.md)|Позволяет использовать отладочные версий функций среды выполнения|  
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Контролирует способ отслеживания выделения памяти отладочным диспетчером кучи|  
  
 Эти флаги можно определить с помощью параметра командной строки /D или с помощью директивы `#define`. Если этот флаг определяется с помощью директивы `#define`, она должна предшествовать оператору включения заголовочного файла, содержащего объявления подпрограмм.  
  
## <a name="see-also"></a>См. также  
 [Глобальные переменные и стандартные типы](../c-runtime-library/global-variables-and-standard-types.md)