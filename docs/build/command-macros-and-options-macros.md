---
title: Макросы команд и макросы параметров | Документация Майкрософт
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
ms.openlocfilehash: 7c66295a42fff6a2e6dde5205fb5d9139e6eceb6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705540"
---
# <a name="command-macros-and-options-macros"></a>Макросы команд и макросы параметров

Макросы команд предопределены для продуктов Майкрософт. Макросы параметров представляют параметры для этих продуктов и не определены по умолчанию. Оба используются в предварительно определенных правилах определения и могут использоваться в блоках описания или правила вывода, определяемые пользователем. Макросы команд можно переопределить для представления всех или части командной строки, включая параметры. Параметры макросы создают строку null, если не определено.

|Продукт Microsoft|Макрос команды|Определяется как|Макрос параметров|
|-----------------------|-------------------|----------------|-------------------|
|Макроассемблер|**КАК И В СЛУЧАЕ**|ml|**AFLAGS**|
|Основные компилятора|**BC**|BC|**BFLAGS**|
|Компилятор C|**"КОПИЯ"**|CL|**CFLAGS**|
|Компилятор C++|**CPP**|CL|**CPPFLAGS**|
|Компилятор C++|**CXX**|CL|**CXXFLAGS**|
|компилятор ресурсов|**Версия-кандидат**|Версия-кандидат|**RFLAGS**|

## <a name="see-also"></a>См. также

[Специальные макросы NMAKE](../build/special-nmake-macros.md)