---
title: Макросы рекурсии
description: Описание макросов, используемых для вызова NMAKE в рекурсивных сеансах.
ms.date: 11/20/2019
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
no-loc:
- MAKE
- MAKEDIR
- MAKEFLAGS
ms.openlocfilehash: f2bda23cb079e4fd7d12cea3598d33b3625c088d
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303148"
---
# <a name="recursion-macros"></a>Макросы рекурсии

Используйте макросы рекурсии для рекурсивного вызова NMAKE. Рекурсивные сеансы наследуют макросы командной строки и переменных среды и сведения Tools. ini. Они не наследуют определенные в файле Makefile правила вывода или спецификации `.SUFFIXES` и `.PRECIOUS`. Существует три способа передачи макросов в рекурсивный сеанс NMAKE: Задайте переменную среды с помощью команды :::no-loc text="SET"::: перед рекурсивным вызовом. Определите макрос в команде для рекурсивного вызова. Или определите макрос в файле Tools. ini.

|Макрос|Определение|
|-----------|----------------|
|**MAKE**|Команда, изначально используемая для вызова NMAKE.<br /><br /> Макрос `$(MAKE)` предоставляет полный путь к NMAKE. exe.|
|**MAKEDIR**|Текущий каталог при вызове NMAKE.|
|**MAKEFLAGS**|Параметры, действующие в настоящее время. Используйте в качестве `/$(MAKEFLAGS)`. Параметр **/f** не включен.|

## <a name="see-also"></a>См. также

[Специальные макросы NMAKE](special-nmake-macros.md)
