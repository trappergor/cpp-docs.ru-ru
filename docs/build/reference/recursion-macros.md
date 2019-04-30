---
title: Макросы рекурсии
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
ms.openlocfilehash: 064bc40906bcf3a126c225585a6df43443b5c38e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319243"
---
# <a name="recursion-macros"></a>Макросы рекурсии

Используйте Макросы рекурсии для вызова NMAKE рекурсивно. Рекурсивные сессии наследуют макросы командной строки и переменных среды и Tools.ini сведения. Они не наследуют правила вывода, определенные в файле makefile или **. СУФФИКСЫ** и **. ЦЕННЫЕ** спецификации. Для передачи макросов рекурсивной сессии NMAKE, задайте переменную среды с НАБОРОМ перед рекурсивный вызов, определить макрос в команде для рекурсивного вызова или определить макрос в Tools.ini.

|Макрос|Определение|
|-----------|----------------|
|**СДЕЛАТЬ**|Команда изначально используется для вызова NMAKE.<br /><br /> Макрос $ предоставляет полный путь к nmake.exe.|
|**MAKEDIR**|При вызове NMAKE текущий каталог.|
|**MAKEFLAGS**|Параметры в данный момент. Использовать в качестве `/$(MAKEFLAGS)`.  Обратите внимание, что /F не включается.|

## <a name="see-also"></a>См. также

[Специальные макросы NMAKE](special-nmake-macros.md)
