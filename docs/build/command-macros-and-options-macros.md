---
title: "Макросы команд и макросы параметров | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 06f5d48395c0395a85c90096bf2dbad8627ac41a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="command-macros-and-options-macros"></a>Макросы команд и макросы параметров
Макросы команд предварительно определены для продуктов Майкрософт. Макросы параметров представляют параметры для данных продуктов, а не определены по умолчанию. Как используются в предварительно определенных правилах определения и может использоваться в блоках описания или правила определения определяемой пользователем. Макросы команд может быть переопределен для представления всех или части командной строки, включая параметры. Макрос параметров создать строку null, если не определено.  
  
|Продукт Майкрософт|Макрос команды|Определяется как|Макрос параметров|  
|-----------------------|-------------------|----------------|-------------------|  
|Макроассемблер|**КАК И В СЛУЧАЕ**|ml|**AFLAGS**|  
|Основные компилятора|**BC**|BC|**BFLAGS**|  
|Компилятор C|**КОПИЯ**|CL|**CFLAGS**|  
|Компилятор C++|**CPP**|CL|**CPPFLAGS**|  
|Компилятор C++|**CXX**|CL|**CXXFLAGS**|  
|компилятор ресурсов|**Версия-кандидат**|Версия-кандидат|**RFLAGS**|  
  
## <a name="see-also"></a>См. также  
 [Специальные макросы NMAKE](../build/special-nmake-macros.md)