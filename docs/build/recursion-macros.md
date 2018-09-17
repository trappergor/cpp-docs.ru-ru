---
title: Макросы рекурсии | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f91a5f327686a522608b6eec9fd7106cbab00028
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702044"
---
# <a name="recursion-macros"></a>Макросы рекурсии

Используйте Макросы рекурсии для вызова NMAKE рекурсивно. Рекурсивные сессии наследуют макросы командной строки и переменных среды и Tools.ini сведения. Они не наследуют правила вывода, определенные в файле makefile или **. СУФФИКСЫ** и **. ЦЕННЫЕ** спецификации. Для передачи макросов рекурсивной сессии NMAKE, задайте переменную среды с НАБОРОМ перед рекурсивный вызов, определить макрос в команде для рекурсивного вызова или определить макрос в Tools.ini.

|Макрос|Определение|
|-----------|----------------|
|**СДЕЛАТЬ**|Команда изначально используется для вызова NMAKE.<br /><br /> Макрос $ предоставляет полный путь к nmake.exe.|
|**MAKEDIR**|При вызове NMAKE текущий каталог.|
|**MAKEFLAGS**|Параметры в данный момент. Использовать в качестве `/$(MAKEFLAGS)`.  Обратите внимание, что /F не включается.|

## <a name="see-also"></a>См. также

[Специальные макросы NMAKE](../build/special-nmake-macros.md)