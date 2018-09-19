---
title: Пустой и неопределенный макрос | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eee6e713715e4709af990878224261a41f5470e3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702641"
---
# <a name="null-and-undefined-macros"></a>Пустой и неопределенный макрос

Пустой и неопределенный макрос разворачиваются в пустые строки, но макрос, определенный как строку null считается определены в выражениях предварительной обработки. Чтобы определить макрос как строку null, укажите никакие символы не только пробелы или символы табуляции после знака равенства (=) в командной строке или командный файл и заключите пустую строку или определение в двойные кавычки (» «). Чтобы отменить определение макроса, используйте **! UNDEF.** Дополнительные сведения см. в разделе [директивы предварительной обработки файла Makefile](../build/makefile-preprocessing-directives.md).

## <a name="see-also"></a>См. также

[Определение макроса NMAKE](../build/defining-an-nmake-macro.md)