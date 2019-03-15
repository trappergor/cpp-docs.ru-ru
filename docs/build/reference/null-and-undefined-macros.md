---
title: Пустой и неопределенный макрос
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
ms.openlocfilehash: 0f4905473dd6914547ad6ac129d34e438992c2af
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827923"
---
# <a name="null-and-undefined-macros"></a>Пустой и неопределенный макрос

Пустой и неопределенный макрос разворачиваются в пустые строки, но макрос, определенный как строку null считается определены в выражениях предварительной обработки. Чтобы определить макрос как строку null, укажите никакие символы не только пробелы или символы табуляции после знака равенства (=) в командной строке или командный файл и заключите пустую строку или определение в двойные кавычки (» «). Чтобы отменить определение макроса, используйте **! UNDEF.** Дополнительные сведения см. в разделе [директивы предварительной обработки файла Makefile](makefile-preprocessing-directives.md).

## <a name="see-also"></a>См. также

[Определение макроса NMAKE](defining-an-nmake-macro.md)
