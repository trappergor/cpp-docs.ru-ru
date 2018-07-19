---
title: Макросы команд и макросы параметров | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab8b1d61c2c4f6ae9125b8eefaf05f791f57b259
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367363"
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