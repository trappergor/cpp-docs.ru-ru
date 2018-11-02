---
title: Неустранимая ошибка C1382
ms.date: 11/04/2016
f1_keywords:
- C1382
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
ms.openlocfilehash: 2b7f6fd878f0d0ba6cde19a3a316a01c390e954a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600607"
---
# <a name="fatal-error-c1382"></a>Неустранимая ошибка C1382

PCH-файл «файл» был перестроен с момента создания «obj». Повторите построение этого объекта

При использовании [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), обнаружен PCH-файл, который новее, чем CIL OBJ-файл, который указывает на нее. Сведения в OBJ-файле CIL-ФАЙЛ является устаревшим. Построение объекта.

C1382 также может возникать при компиляции с параметром **/Yc**, но также передается несколько файлов исходного кода для компилятора.  Чтобы устранить проблему, не используйте **/Yc** при передаче нескольких файлов исходного кода для компилятора.  Дополнительные сведения см. в разделе [/Yc (создать предкомпилированный заголовочный файл)](../../build/reference/yc-create-precompiled-header-file.md).