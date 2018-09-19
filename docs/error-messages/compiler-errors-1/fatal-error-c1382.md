---
title: Неустранимая ошибка C1382 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1382
dev_langs:
- C++
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a5a6ce312c5ef886ef25e8de46e6d3376eded2e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030661"
---
# <a name="fatal-error-c1382"></a>Неустранимая ошибка C1382

PCH-файл «файл» был перестроен с момента создания «obj». Повторите построение этого объекта

При использовании [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), обнаружен PCH-файл, который новее, чем CIL OBJ-файл, который указывает на нее. Сведения в OBJ-файле CIL-ФАЙЛ является устаревшим. Построение объекта.

C1382 также может возникать при компиляции с параметром **/Yc**, но также передается несколько файлов исходного кода для компилятора.  Чтобы устранить проблему, не используйте **/Yc** при передаче нескольких файлов исходного кода для компилятора.  Дополнительные сведения см. в разделе [/Yc (создать предкомпилированный заголовочный файл)](../../build/reference/yc-create-precompiled-header-file.md).