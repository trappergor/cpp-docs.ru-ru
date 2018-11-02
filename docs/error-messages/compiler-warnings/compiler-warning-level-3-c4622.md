---
title: Предупреждение компилятора (уровень 3) C4622
ms.date: 11/04/2016
f1_keywords:
- C4622
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
ms.openlocfilehash: 88a41c7f9edb1d2a9f6d4547336a77bd5e362882
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575335"
---
# <a name="compiler-warning-level-3-c4622"></a>Предупреждение компилятора (уровень 3) C4622

перезапись отладочной информации, сформированной во время создания предкомпилированного заголовка в объектном файле: "файл"

Информация CodeView в указанном файле была утеряна при выполнении компиляции с параметром [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (использование предкомпилированных заголовков).

Переименуйте объектный файл (с использованием параметра [/Fo](../../build/reference/fo-object-file-name.md)) при создании или использовании файла предкомпилированного заголовка и выполните компоновку с использованием нового объектного файла.