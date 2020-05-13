---
title: Неустранимая ошибка NMAKE U1051
ms.date: 11/04/2016
f1_keywords:
- U1051
helpviewer_keywords:
- U1051
ms.assetid: fede5cd5-dac3-47b7-b86d-e1acfb78699f
ms.openlocfilehash: 9c6b939c97f993e42049677292374377d825d474
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193684"
---
# <a name="nmake-fatal-error-u1051"></a>Неустранимая ошибка NMAKE U1051

недостаточно памяти

Программе NMAKE не хватило памяти, включая виртуальную память, так как файл makefile слишком большой или сложный.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки

1. Освободите место на диске.

1. Увеличьте размер файла подкачки Windows NT или файла подкачки Windows.

1. Если используется только часть файла makefile, Разделите файл makefile на отдельные файлы или используйте **.** Значение, если директивы предварительной обработки позволяют ограничить объем обработки, которую должен ОБРАБОТАТЬ NMAKE. **! Если** директивы if включают **! Если**, `!IFDEF`, **! IFNDEF**, **! ELSE IF**, **! ELSE** `IFDEF`и **! ИНАЧЕ** `IFNDEF`.
